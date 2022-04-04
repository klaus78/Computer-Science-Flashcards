<details>
<summary>What are the differences between a library and a framework?</summary>

A library and a framework are both a piece of external code that you can use in your application. 

The difference between library and framework is what is called inversion of control. In short, when you call a method from a library, 
you are in control. But with a framework, the control is inverted: the framework calls you. 

A library allows you to control where you want to put and build your code, while a framework is already in set of the flow and has places already set for you to place your code. In other words, a framework defines a structure for your application and a set of places
where you can put your code. 

</details>

## Multithreading

<details>
<summary>What is a race condition?</summary>
A race condition happens when a number of threads can access a common resource without synchronization. Because the order of the threads accessing the resource depends on the scheduling algorithm and we do not know it, the final result is uncertaint.
</details>