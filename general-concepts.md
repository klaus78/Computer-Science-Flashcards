<details>
<summary>What are the differences between a library and a framework?</summary>

A **library** and a **framework** are both a piece of external code that we can use in our application.

The difference between library and framework is what is called inversion of control. In short, when we call a method from a library,
we are in control. But with a framework, the control is inverted: the framework calls we.

A library allows us to control where we want to put and build our code, while a framework has places already set for us where to place our code. In other words, a framework defines a structure for our application and a set of places where we can put our code.
</details>



## Concurrency and Parallelism

<details>
<summary>What is the difference between concurrency and parallelism?</summary>

**Concurrency** refers to an application handling more than a task at the same time on a single-cpu unit. The OS takes care of switching the context between tasks so that each task can use the cpu for a portion of time.

**Parallelism** refers to running multiple computations simultaneously. It cannot be achieved on a single-cpu unit but it requires multiple cpu units.

Often, concurrency is the problem (e.g., many HTTP requests hitting a web server) and parallelism is the answer (e.g., the web server being able to serve all the requests using parallel processes).
</details>


<details>
<summary>What is the difference between multi-processing and multi-threading?</summary>

**Multi-processing** involves the creation of separate processes, that run completely isolated one from the other.

**Multi-threading** requires the creation of *lightweight* processes, called **threads** that all share the same memory and therefore are not isolated from each other.
</details>

<details>
<summary>What is a race condition?</summary>

A **race condition** happens when a number of threads can access a common resource without synchronization. Because the order of the threads accessing the resource depends on the scheduling algorithm and we do not know it, the final result is uncertaint.
</details>


<details>
<summary>What is the difference between deadlock and starvation?</summary>

A **deadlock** is when a process or a thread requires a resource that is hold by another process or thread, that in turn requires a resource owned by the former process. Since none of the processes are going to release the resource they hold, the two processes cannot continue their execution.

A **starvation** is when a process or a thread is unable to acquire a resource because it it repeatedly stolen by another parallel process.
</details>

<details>
<summary>What is a lock?</summary>

A **lock** is a resource used to *protect* another resource that parallel processes are going to acquire in turn.
There are different implementation of locks, depending on the context they are applied. Some examples are *spin-locks*, *sempahores*, *mutexes* and so on.
</details>

<details>
<summary>What are the different types of locks?</summary>

There are the following types of **locks**:

* **Semaphore**  is a lower-level object. You might well use a semaphore to implement a monitor. A semaphore essentially is just a counter. When the counter is positive, if a thread tries to acquire the semaphore then it is allowed, and the counter is decremented. When a thread is done then it releases the semaphore, and increments the counter.

    If the counter is already zero when a thread tries to acquire the semaphore then it has to wait until another thread releases the semaphore. If multiple threads are waiting when a thread releases a semaphore then one of them gets it. The thread that releases a semaphore need not be the same thread that acquired it.

    A monitor is like a public toilet. Only one person can enter at a time. They lock the door to prevent anyone else coming in, do their stuff, and then unlock it when they leave.

    A semaphore is like a bike hire place. They have a certain number of bikes. If you try and hire a bike and they have one free then you can take it, otherwise you must wait. When someone returns their bike then someone else can take it. If you have a bike then you can give it to someone else to return --- the bike hire place doesn't care who returns it, as long as they get their bike back.


* **Mutex** is for multiprocess synchronization. Usually, mutexes are provided by the OS kernel and libraries/frameworks simply provide an interface to invoke it. This makes them heavy-weight/slower, but they work across threads on different processes. 

* **Monitor** is for multithread synchronization within the same process. Usually, the implementation of monitors is faster/light-weight, since it is designed for multi-threaded synchronization within the same process. Also, usually, it is provided by a framework/library itself (as opposed to requesting the OS).
</details>



