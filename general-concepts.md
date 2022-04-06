<details>
<summary>What are the differences between a library and a framework?</summary>

A library and a framework are both a piece of external code that we can use in our application.

The difference between library and framework is what is called inversion of control. In short, when we call a method from a library,
we are in control. But with a framework, the control is inverted: the framework calls we.

A library allows us to control where we want to put and build our code, while a framework is already in set of the flow and has places already set for us to place our code. In other words, a framework defines a structure for our application and a set of places
where we can put our code.

</details>

## Concurrency and Parallelism


<details>
<summary>What is the difference between **concurrency** and **parallelism**?</summary>

**Concurrency** is the way the application behaves, meaning how requests for data and interaction are sent to it; **parallelism** is a way an application can carry on its tasks.

Often, concurrency is the problem (e.g., many HTTP requests hitting a web server) and parallelism is the answer (e.g., the web server being able to serve all the requests using parallel processes).
</details>


<details>
<summary>What is the difference between *multi-processing* and *multi-threading*?</summary>

**Multi-processing** involves the creation of separate processes, that run completely isolated one from the other.
**Multi-threading** requires the creation of *lightweight* processes, called **threads** that all share the same memory and therefore are not isolated each other.

</details>

<details>
<summary>What is a race condition?</summary>
A race condition happens when a number of threads can access a common resource without synchronization. Because the order of the threads accessing the resource depends on the scheduling algorithm and we do not know it, the final result is uncertaint.
</details>


<details>
<summary>What is a lock?</summary>

A **lock** is a resource used to *protect* another resource that parallel processes are going to acquire in turn.
There are different implementation of locks, depending on the context they are applied. Some examples are *spin-locks*, *sempahores*, *mutexes* and so on.
</details>



<details>
<summary>What is the difference between *deadlock* and *starvation*?</summary>

A **deadlock** is when a process or a thread requires a resource that is hold by another process or thread, that in rutn requires a resource owned by the former process. Since none of the processes are going to release the resource they hold, the two processes cannot continue their execution.

A **starvation** is when a process or a thread is unable to acquire a resource because it it repeatadly stolen by another parallel process.
</details>
