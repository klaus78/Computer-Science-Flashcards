<details>
<summary>What are the differences between a library and a framework?</summary>

A library and a framework are both a piece of external code that we can use in our application. 

The difference between library and framework is what is called inversion of control. In short, when we call a method from a library, 
we are in control. But with a framework, the control is inverted: the framework calls we. 

A library allows us to control where we want to put and build our code, while a framework is already in set of the flow and has places already set for us to place our code. In other words, a framework defines a structure for our application and a set of places
where we can put our code. 

</details>

## Multithreading

<details>
<summary>What is a race condition?</summary>
A race condition happens when a number of threads can access a common resource without synchronization. Because the order of the threads accessing the resource depends on the scheduling algorithm and we do not know it, the final result is uncertaint.
</details>