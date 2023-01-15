<details>
<summary>Question?</summary>

Your answer
</details>





## Design pattern


<details>
<summary>What are the differences between Abstract Factory and Factory design patterns?</summary>


</details>




<details>
<summary>What are disadvantages of the Singleton pattern?</summary>

The **Singleton pattern** has a number of disadvantages:
* it creates a global object that classes references directly rather getting it injected in the constructor.

</details>




<details>
<summary>What are the differences between the MVVM and the MVC patterns?</summary>
</details>

## Operating systems

<details>
<summary>What are POSIX systems?</summary>

The **Portable Operating System Interface**, better known as **POSIX**, is a set of standards specified by the Institute of Electrical and Electronics Engineers (IEEE). It helps maintain portability and compatibility between different operating systems.

POSIX defines both the system- and user-level application programming interfaces (API), along with command line shells and utility interfaces, for software compatibility (portability) with variants of Unix and other operating systems.

**Cygwin** is a POSIX-compatible programming and runtime environment that runs natively on Microsoft Windows. Under Cygwin, source code designed for Unix-like operating systems may be compiled with minimal modification and executed.
</details>

<details>
<summary>What are the main techniques of interprocess communication?</summary>

These are a few different approaches for Inter- Process Communication:

1. **Pipes**: Pipe is widely used for communication between two related processes. This is a half-duplex method, so the first process communicates with the second process. However, in order to achieve a full-duplex, another pipe is needed.
1. **Shared Memory**: Shared memory is a memory shared between two or more processes that are established using shared memory between all the processes. This type of memory requires to protected from each other by synchronizing access across all the processes.
1. **Message Queue**: A message queue is a linked list of messages stored within the kernel. It is identified by a message queue identifier. This method offers communication between single or multiple processes with full-duplex capacity. 
1. **Direct Communication**: In this type of inter-process communication process, should name each other explicitly. In this method, a link is established between one pair of communicating processes, and between each pair, only one link exists.
1. **Indirect communication**: Indirect communication establishes like only when processes share a common mailbox each pair of processes sharing several communication links. A link can communicate with many processes. The link may be bi-directional or unidirectional.
1. **Message Passing**: It is a mechanism for a process to communicate and synchronize. Using message passing, the process communicates with each other without resorting to shared variables.
    IPC mechanism provides two operations:

    * Send (message)- message size fixed or variable
    * Received (message)
1. **FIFO**: Communication between two unrelated processes. It is a full-duplex method, which means that the first process can communicate with the second process, and the opposite can also happen.
</details>






## UML
<details>
<summary>What is the difference between the dashed line and the solid line?</summary>

The **solid line** in code is
```Csharp
class ClassA {
    // global instance
    ClassB classB = new ClassB();
}
```

The dotted line `---->` in code is
```Csharp
class ClassA {
    // case 1
    void someMethod(ClassB classB);

    // or
    // case 2
    void someOtherMethod() {
        // local instance
        ClassB classB = new ClassB();
    }
}
```
</details>

## Android

<details>
<summary>What is a broadcast receiver?</summary>

**Broadcast receiver** is used for listening for system level events like incoming calls, SMSs,  
</details>

<details>
<summary>What is the content provider?</summary>

The **content provider** is used to share data between various applications.
</details>

<details>
<summary>What is an intent?</summary>

An **intent** is a messaging object that is used to request an action from other components. For example it can be used
to launch an activity, send an email or SMS, display a web page etc. 
</details>


<details>
<summary>What is the use of <b>Bundle</b> in Android?</summary>

**Bundles** are used to pass data between activities.
</details>

<details>
<summary>What is the difference between explicit and implicit intents?</summary>

With an **explicit intent** it is specified what activity should handle it. 

With an **implicit intent** you just define the type of action and the Android system will check for the proper component.
</details>

<details>
<summary>What are the different launch modes of an Activity in Android?</summary>

In Android there are the following **launch modes**:
* **standard**: it creates a new instance of an activity each time that activity is visualized.
* **singleTop**: a new instance of an activity is created only when the activity is not present on the top. If an instance already exists on top, then that activity is reused an the intent will be passed to the `onNewIntent()` method. This makes sure that only a single instance of the activity will remain on top.
* **singleTask**: only an instance of an activity can survive in a task. If an activity does not exist, a new task is created and the activity is placed at the root. If an activity is already present on top, then a new instance is not created and the `onNewIntent()` method is invoked. If an activity is already present but not on top, it pops all other activities so that the current activity is on top and the `onNewIntent()` method is invoked.
* **singleInstance**: it essentially means *single instance in a single task*. This launch mode is similar to *singletask* but a new task is created with the new activity and there will be two stacks. However, if an instance of the activity exists in a different task, then the `onNewIntent()` method is called for that activity.

</details>

<details>
<summary>What is the difference between singleTask and singleInstance launch modes?</summary>

In **singleTask**, a new task is launched and that new task can contain other activities as well.

In **singleInstance**, a new task is launched and that new task cannot contain other activities.
</details>


<details>
<summary>What is a task in Android?</summary>

In Android a **task** is a collection of activities that the user interacts with when using applications. These activities
are arranged in the so called *back stack*.

These activities can belong to a single application but could also belong to two different applications. For example if you want to diplay a street map in your application, there is already activity that can do that. As a result in the task there is the activity of your class and an activity of the map viewer application (say Google Maps).
</details>

<details>
<summary>What is the difference between compileSdkVersion and targetSdkVersion?</summary>

**compileSdkVersion** is the version of API the application is compiled against.

**targetSdkVersion** indicates that you have tested the app on the version specified.
</details>



