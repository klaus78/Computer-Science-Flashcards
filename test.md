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

## Networking
<details>
<summary>What are the seven layers of the ISO / OSI?</summary>

The International Organization for Standardization (ISO) developed the Open Systems Interconnection (OSI) model, which allows different communication systems to communicate via standard protocols.

The OSI model is divided into seven layers, as follows

1. **Physical Layer** takes care of transmission and reception of raw bytestreams over a physical medium.
1. **Data Link Layer** performs the most reliable node to node delivery of data. It forms frames from the packets that are received from network layer and gives it to physical layer. It also synchronizes the information which is to be transmitted over the data. Error controlling is easily done. The encoded data are then passed to physical
1. **Network Layer**: controls the source to destination delivery of data packets across multiple nodes (routing). Network layer is implemented by network devices such as routers.
1. **Transport Layer** is responsible for delivery of an entire message from an application program on the source device to a similar application program on the destination device. Protocols are TCP and UDP.
1. **Session Layer** is responsible for establishing, managing, synchronizing and terminating sessions between end-user application processes.
1. **Presentation Layer** ensures that the message is presented to the upper layer in a standardized format. It deals with the syntax and the semantics of the messages (encryption - compression).
1. **Application Layer** is the topmost layer of the OSI model. It specifies the interfaces and supports services to the end users for network access. Some examples are HTTP, FTP and SMTP.

The basic difference between network layer and transport layer is that transport layer protocol provides logical communication between processes running on different hosts , whereas network layer protocol provides logical communication between processes within the same host.
</details>

<details>
<summary>Hub vs switch vs router?</summary>

A **switch**, also known as an Ethernet switch and network switch, is a piece of networking hardware used on WANs and LANs. A switch connects multiple devices on a network and manages packets according to the IP address of the device.

In a network, a **router** is layer-3 networking hardware used at the network layer of the OSI design. A router can connect a network to another network and transfer data between them. Unlike the hub, a router will use IP address information to transfer IP packets.

A **hub** is a simple networking device that connects several devices in a Local Area Network. Unlike the other two devices I have mentioned before, a hub does not filter information. Instead, it copies the incoming data to all the devices connected to the network and vice versa. Network hubs, also known as Ethernet hubs, are also used to enhance the network distance. However, these devices do not recognize the devices based on the IP address. On the other hand, the system simply copies information as a part of the routine.

</details>

## Web
<details>
<summary>What is a single page application?</summary>

A **single-page application (SPA)** is a web application or website that interacts with the user by dynamically rewriting the current web page with new data from the web server, instead of the default method of a web browser loading entire new pages. The goal is faster transitions that make the website feel more like a native app.

In a SPA, a page refresh never occurs; instead, all necessary HTML, JavaScript, and CSS code is either retrieved by the browser with a single page load,[1] or the appropriate resources are dynamically loaded and added to the page as necessary, usually in response to user actions.
</details>

<details>
<summary>What is Razor?</summary>

**Razor** is a markup syntax that lets you embed server-based code into web pages using C# and VB.Net. It is not a programming language. It is a server side markup language.

Server-based code can create dynamic web content on the fly, while a web page is written to the browser. When a web page is called, the server executes the server-based code inside the page before it returns the page to the browser. By running on the server, the code can perform complex tasks, like accessing databases.
</details>

<details>
<summary>What is paging?</summary>

**Paging** refers to getting partial results from an API which is useful when the API result is very large.
</details>

<details>
<summary>What is filtering?</summary>

**Filtering** refers to showing only part of the results of a web api call.
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



