---
layout: post
title: "Further adventures in xv6"
date: 2020-03-28
---

I had implemented a semaphore in my little "cotton threads" 1:1 thread wrapper
library in xv6. Now, the implementation is as follows:

	void sem_init(semaphore_t *s, int n)
	{
	  slock_init(&s->guard);
	  s->count = n;
	  qinit(&s->waitq);
	}

	void sem_up(semaphore_t *s)
	{
	  int pid;
	  slock_acquire(&(s->guard));
	  s->count++;
	  if(s->count <= 0){
	    pid = deq(&(s->waitq));
	    unpark(pid, &(s->count));
	  }
	  slock_release(&(s->guard));
	}

	void sem_down(semaphore_t *s)
	{
	  int pid;
	  slock_acquire(&(s->guard));
	  s->count--;
	  if(s->count < 0){
	    pid = getpid();
	    enq(&(s->waitq), pid);
	    slock_release(&(s->guard));
	    park(&(s->count));
	  }
	  else{
	   slock_release(&(s->guard));
	  }
	}

I suppose this is not very efficient, and uses specially-created *park* and
*unpark* calls. I can't *formally* prove it's correctness either. But I was
pretty confident that this should work.

And somehow, in this implementation where each access to the contents of the
semaphore are protected by guard locks, threads were going to sleep, and were
not being woken up. In addition to this, random segfaults were happening in
*free*.

Now, for a page fault to happen, there should be an out-of-bounds
access. And if you observe the code, *all queue operations* are protected by a
lock. So there is no reason of there being a mess in pointers. 

I started suspecting the correctness of my spinlocks, which and imagining that
the control was "leaking" through the spinlock and playing with pointers. I
checked the code- I did not think there was a reason to doubt it- (In fact, I
had copied the xv6 kernel-space spinlock implementation, removed the *cli* and
*sti* instructions, logging, and had passed it off as "*slock_t*". 

Now here is the kicker- the queue was implemented using linked nodes, which
means I was making calls to the memory allocator function, malloc() and free().
xv6's uses KnR's memory allocator implementation. Here is a snippet of code from
the memory allocator- 

	union header {
	  struct {
	    union header *ptr;
	    uint size;
	  } s;
	  Align x;
	};


and

	void
	free(void *ap)
	{
	  Header *bp, *p;

	  bp = (Header*)ap - 1;
	->for(p = freep; !(bp > p && bp < p->s.ptr); p = p->s.ptr)
	    if(p >= p->s.ptr && (bp > p || bp < p->s.ptr))
	      break;
	  if(bp + bp->s.size == p->s.ptr){
	  ...
          ...
 
Notice that the memory allocator *itself* uses a list of allocated memory
blocks..

As it turns out, the producer-consumer code I was running as a test uses three
semaphores (traditionally called *empty*, *full*, and a binary semaphore used as
a *mutex*. Access to the queues of each of these semaphores will be
synchronized. However, there is nothing stopping *parallel* access to two
different queues at the same time. *And all the queues use the same memory
allocator, and the same free-space-list, as they are being used by threads of
the same process, which share an address space.* **And there is no lock on the
free-node-list itself**. This is fair, because the original xv6 does not include
*clone* it need not worry about this. But now.. it opens the door to the dungeon
dimensions, allowing all sorts of dangerous beasts to leak into our world.
What's so bad about this. How about **the same piece of memory is allocated
twice**? Now, I have not verified this, and I do not wish to take a stroll 
in the dungeon dimensions.

But I did this- I replaced the implementations of the queue functions to use an
array instead of a list- and voila! It worked. I suppose a better solution would be
to put a big spinlock on the free node list used by the allocator. But I have
had enough suffering for today.

> There are thread-safe implementations of malloc in the GNU C library. I
> suppose the purpose of the KnR implementation (much like xv6) is education
> rather than use.
