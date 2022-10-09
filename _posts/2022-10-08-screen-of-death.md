---
layout: post
title: Return to the Black Screen of Despair or "There and back again"
date: 2022-10-08
---

After an afternoon spent trying to fix a keyboard key of my 30$ laptop (which I
got from facebook marketplace), my Manjaro threw up a black screen of despair
after reboot. A bit about my laptop- its a lenovo G520 from ~2013, has 100GB
SSD, and came with a Windows 8 license when I bought it off Facebook
Marketplace. 30$ was a dream deal- I wanted a sturdy laptop which would let me
write code, use the browser, read, and watch videos. I have this superiority
complex about using old hardware- CPUs today are insanely fast, and there is no
reason to buy the latest hardware unless you want to run bloatware (aka
Windows). So I make it a point to buy second hand. But 30$ was an insane price.
If there is an afterlife, I'm confident that the Postdoc who sold his laptop to
me is going to heaven. When I asked about the reason behind him selling at so
low a price, his reply was "You can give me more if you want". I stopped asking
questions and made the deal. And hadn't regretted it ever since. Until today.

My previous laptop never died completely. I regret the fact that I wasn't able
to use its full value. The processor or peripheral circuitry usually does not
fail. But mechanical components can. Fans have always been the bugbears of my
laptops. My Dell Inspirion was bent on retirement, and decided that the cooling
fan was not going to rotate anymore.  The fan stopped working once. I replaced
it, after which it stopped working again. Then found out that I could make it
work for a few days by routinely cleaning it with a can of compressed air (1
can every month for one year- 36$. laptop repair- 90$. New laptop- 200$). In a
"Hail Mary" manuever, the Inspirion made the keyboard go kaput (a-la Polk and
Mahone from "The Wire'), after which I allowed the old workhorse to retire with
pension. Moral of the story- don't buy delicate, light laptops- buy heavy
monsters with click-click keyboards. The Lenovo G520 (my new instrument) 
was exactly that. Until today.

With two failures in one day, (the second of which was a blank screen), I began
to think thoughts of despair. I imagined a scenario where I had to purchase a brand-new one-
a thought which turned my stomach. How much could I expect from a 30$ laptop anyway? My past 
had finally caught up with me, and it was time to pay for all the times when I had cheated
the OEM gods of their rightful due. 

Thinking these dreadful thoughts, I went on the Manjaro forums, and found a
[post](https://forum.manjaro.org/t/fix-system-doesn-t-boot-boots-to-a-black-screen-or-stops-at-a-message/3906)
that described my problem perfectly, and followed the "First thing to try". 5 minutes later, I was back
at the Manjaro graphical login screen. Here's what I did:

```
Ctrl + Alt + F2 // this opens a text console
```

The login shell came up. I could breathe.

```
$ sudo pacman-mirrors -f3 // worked
$ sudo pacman -Syyu // NOT ENOUGH SPACE!
```

Here's what had happened. The blank screen _was_ the laptop's fault- but not
in a dangerous way. Manjaro had run out of space, which (I hypothesize) was preventing the 
GUI login shell from running. This was because I had been downloading
a lot of ... Uhh... _Creative Commons shows and movies_ recently, and Manjaro had 
a mere 50G partition. 

I traced the folders consuming most of the space.

```
$ du -ah -d 1 
// much better than du 
// -a -> files and directories
// -h -> human readable- I want K / M / G, not byte counts
// -d 1 -> depth 1 -> otherwise du traverses the whole
// tree rooted at $pwd, rendering the output unactionable
```

Most of the space was consumed by ... Uhh .. Creative Commons shows and movies
that I had downloaded. I deleted them. Manjaro had free space.

```
sudo shutdown now -r
```

And, dear reader, here I am, typing this out on the very same laptop. As a reward 
for reading till the end, here are a few more unsolicited obvious "pearls of wisdom".

1. When a program you have written is not working the way you expect it to, it
   is _always your fault_.  No, the language implementation is not wrong. No,
the system call does not have a bug. No, this is not the result of a
single-event upset, no matter how many bloggers claim that it has happened with
them. Neither they, nor you are Sanjay Ghemawat or Jeff Dean. In the same way,
when your system crashes, _it is a software failure_. No, the CPU did not fail.
No, there has not been RAM corruption. No, there is not a loose connection on
your motherboard. Not these days anyway. Your hardware will live forever. As
long as you have backup, you are one disk format and reinstallation away from
getting back online. I like to be reminded of these things once in a while (and I _am_).

2. Don't buy top-of-the line spec (or even brand-new) PCs/Laptops unless you want to:
	- Keep up with the softies (run the latest version of Windows(TM).
	- Run ("pcmasterrace") games
	- Run simulations (really, try to get a server from your univ, this 
_will_ ruin your laptop).

Fin.
