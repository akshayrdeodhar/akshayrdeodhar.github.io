---
layout: page
title: About
---

I am a master's student studying Computer Science at Georgia Tech. In my first two semester and my internships, I learned to hack computer systems. In my last semester, I'll be taking "Ivory Tower" math-y courses. (for science, and for the children!). 

I'm interested in working in infrastructure, compilers, databases and HPC.
I'm inclined towards projects that lie at the intersection of implementation
and theory. From a theoretical standpoint, I'm interested in parallelism,
concurrency, algorithms, and programming languages. At Georgia Tech, I've taken
Compiler Optimizations, Advanced Operating Systems, Database System
Implementation (internals), Datacenter Networks and Systems, and Machine Learning. In other
words, I've hacked LLVM, KVM,
[buzzDB](https://buzzdb-docs.readthedocs.io/en/latest/index.html), and have
read loads of [systems research
papers](https://saeed.github.io/CS8803_DNS_Spring2022/syllabus.html).

# Experience

## 2023- Back to Georgia Tech

In Spring 2023, I'll be returning as a teaching assistant for CS 6210. Besides that, I'm going to take two math-y courses- Parallelizing Compilers and Graduate Algorithms, and the last semester of my education.

## 2022- Georgia Tech, Nvidia, and an AI chip startup

In Spring 2022, I worked as a teaching assistant for Prof Kishore
Ramachandran's course, CS 6210 Advanced Operating Systems.

I fulfilled my long-cherished dream of working in a chip company this
year, **twice**. 

In summer, I interned at **Nvidia**, working in the [Fleet
Command](https://www.nvidia.com/en-us/data-center/products/fleet-command/)
team, where I wrote a new service for zero-touch provisioning of GPU-enabled
edge devices. I also built a prototype where I integrated the Fleet Command log
collection service with an internal ELK data platform, and researched a
binary-diff mechanism for making over-the-air updates more efficient. The team
is wonderful, filled with people having different areas of expertise, and with
two common traits- everyone is really nice and helpful.

In the fall, I interned at an AI Chip startup in the SF Bay area, working on
the compiler for a Domain Specific Language (DSL) used for implementing
[PyTorch-style
operators](https://dev-discuss.pytorch.org/t/where-do-the-2000-pytorch-operators-come-from-more-than-you-wanted-to-know/373)
on their chip. The architecture is very different from whatever else is on the
market. This was the place where I finally earned my compiler stripes. Other
than that, I met a lot of people who were really smart, enthusiastic, and fun
to be around.

## 2021- Veritas Technologies

As a final year undergrad at College of Engineering Pune, I did a co-op /
internship at Veritas Technologies in the Infoscale team, working on a
Kubernetes Container Storage Interface driver for Infoscale. Essentially, it is
a microservice that implements [this gRPC
interface](https://github.com/container-storage-interface/spec). Kubernetes will
call this microservice for allocating volumes for containers that it schedules.
This was an awesome experience, because it allowed me to work with Kubernetes
Custom Resources, code-generation, and the CSI spec. 

## 2020- IIT Kanpur

Before that, I did a research internship at IIT Kanpur in December 2019-20 and
[summer 2020](https://www.cse.iitk.ac.in/users/swarnendu/alumni.html) with
Prof. Swarnendu Biswas, where I worked on sparse matrix format selection for
Sparse Matrix-Vector Multiplication (one of the ways you can run PageRank) on
GPUs and high performance processors. During the internship, I created a
semi-supervised format selection model which only requires labelling of a 10%
subset of the training set, with a view to inexpensively create models for
different processor architectures and enhance portability.  During the winter
and in early summer I studied NVIDIA CUSP CUDA kernels for Sparse Matrix Vector
multiplication, and created schemes for creating representative sparse matrix
samples for format selection. Also proposed new statistical features for
characterising sparse matrices with respect to these kernels. Our work resulted
in a paper at ICPP 2021's DUAC workshop. Have a look at it
[here](https://www.cse.iitk.ac.in/users/swarnendu/files/papers/spmv-duac21.pdf).

## 2017 - 2021- COEP Satellite Team

I was the ADCS Subsystem Lead at COEP's Satellite Initiative. The team is working on
designing (and hopes to launch) a Solar Sailing satellite- one which maneuvers
its orbit purely using solar radiation. My work involved designing and testing
solar sail orientations for maximizing orbit rise. I built a continuous thrust
propagator using the Python API of GMAT's General Mission Analysis Tool, and
validated it. I found some anomalous trends in the satellite's orbit, in the
simulations, and found an interesting explanation for these anomalies- the
fact that the earth [is not actually
spherical](https://en.wikipedia.org/wiki/Nodal_precession). Before that I
worked on adding modules to a C-based satellite orientation simulation in an
*ooold* codebase. Other than that, I used to hang around in the lab being generally
chatty and poking my nose in when when our onboard computer folks sat
discussing BCH, stackless coroutines, and deadlocks. If you are a COEP student,
consider joining the team the next time they conduct inductions! CSAT has got
really cool stuff going on.

## Misc

Besides this, the other things from undergrad that I loved doing were [hacking
xv6](https://github.com/akshayrdeodhar/xv6-kthreads), building an AI chess game,
whom I named "[Trillian](https://github.com/akshayrdeodhar/trillian)" (a Hitch-Hiker's Guide to the Galaxy reference), and my
[brief tryst](https://github.com/akshayrdeodhar/sicp) with the charms of Functional Programming and
Scheme when I was young and carefree. 


# Life

This is a personal website, but it is also my blog- the posts are scattered and
mostly not deeply CS related, but hey! Other stuff is fun too! If you want to
see my code, look at my [github](https://github.com/akshayrdeodhar).

Inspite of my respect for Emacs and Arch users, I opt to use Vim (sometimes
_VSCode_) and Manjaro, and have grown to love the GUI package manager. I'm an
open source fan.  Recently, I started using Clang instead of GCC.

I hope to do things in life other than CS- I've at different points in time
been really into trekking, Sci-Fi and Fantasy, Wodehouse, Douglas Adams,
classical music (western and Hindustani), Chess, and Badminton. I enjoy
cooking, and am becoming better at it, one dish at a time. I've written some
weird but entertaining articles for our college magazine, and served as editor
for a year. I have a long-unfulfilled wish of running a Dungeons and Dragons
campaign in a highly detailed steampunk world. I learned a bit of sculling
during my summer break after second year, but have a tendency to fall into the
Mutha river from the stablest of boats. Now, I'm learning rock-climbing.
