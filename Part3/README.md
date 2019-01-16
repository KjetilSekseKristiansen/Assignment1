# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
 > Concurrency is the ability of different parts of a program to be executed "out-of-order" without it affecting the final outcome. Said in other words it is the ability for a program to be decomposed into indepent parts which can be manipulated independently of each other.
 > Several instructions are carried out simultaneously, in paralell. 
 >  Concurrency is about dealing with a lot of things at once, but parallelism is about executing lots of things at once. In concurrency a processor can deal with more tasks at the same time, but never execute them at the same time. 
 
 ### Why have machines become increasingly multicore in the past decade?
 > We have reached limit for how high a clock frequency can be in the processor without making it very energy inefficient or dangerously hot. 
 
 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 > Makes paralell programming way easier to handle as concurrent tasks can be executed in at the same time (because of their independency of each other). Faster runtime is the motivation for concurrency. 
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > *Your answer here*
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 > *Your answer here*
 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 > They all create a thread
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > Basically prevents multiple threads from executing Python bytecodes at the same time. This is necessary because Python's memory management is not thread-safe. 
 > The GIL must be held by the current thread before it can safely access Python objects when programming multi-threaded. It prevents multithreaded python programs from taking full advantage of multiprocessor systems in some situations. Only programs spending a lot of time inside the GIL is subject to this disadvantage. Actions like I/O, image processing and NumPy number crunching happens outside GIL. 
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > Can use the "multiprocessing" module. works well with workloads that consist of small numbers of long running computational tasks. Can use a python implementation that doesnt rely on the GIL like Jython or IronPython. Can nalso use process-based concurrency rather than thread-based concurrency as a work around. 
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > This function sets the maximum number of CPUs that can be executing simultaneously and returns the previous setting. Does not change current configuration if n < 1. 
