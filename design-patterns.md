## Design patterns

<details>
<summary>What are the three types of design patterns from the gang-of-four book?</summary>

The three types of design patterns from the gang-of-four book are

* **Creational patterns**: are pattern for object instantiation.
* **Structural patterns**: are patterns defining the structure and relationships among objects.
* **Behavioral patterns**: are patterns about how objects interact and communicate at runtime.
</details>


<details>
<summary>What are the main <b>creational</b> design patterns? When are they used?</summary>

**Creational** design patterns are patterns responsible for the creation of objects.

The main **creational** design patterns are: 

* **Abstract factory** is used when we need to create families of related objects. For example we want to create instances
of bank account (normal account or stock count) and identity card (personal id or passport). 
* **Factory** is used when we want to create different flavors of a similar class. For example assume we have the abstract `CreatePizza` class and we create the concrete classes ``CreatePizzaMargherita`` and `CreatePizzaQuattroStagioni`.
* **Builder**: is used when we have a complex object whose creation requires a number of intermediate steps. 
* **Prototype** is used when we want to create a deep-copy of an existing object.
</details>

<details>
<summary>What are the main <b>structural</b> design patterns? When are they used?</summary>

**Structural** design patterns define how the objects are structured and organized.

The main structural patterns are:
* **Adapter**: is used when two objects with mismatching interfaces want to communicate. Let's say `class1` wants to communicate with `class2` but their interfaces are incompatible. The solution is to create an ``IAdapter`` interface that implements the `class1` interface and  an ``Adapter `` class implementing `IAdapter`. The `Adapter` class holds a reference to `class2`. At this point `class1` can interact with `class2` through `Adapter`. 
* **Bridge**: this patterns shows that composition is more flexible than inheritance. This pattern is used to make changes to different aspects of a system independently of each other.

  Suppose that we have a product and a delivery service. If we set the delivery service type inside a product class and we create a new delivery service, we also need to create a new product class with that new delivery service.

  A more flexible solution is that product class references an abstract class of delivery service. In this way we can add a new delivery service without having to create a new product class. 

* **Composite**: is used when we have a tree-like set of objects. For example we could have a large container box that contains smaller fridge boxes and those fridge boxes contain food boxes. This is a tree structure. We create an interface ``IComposite``
with the `getPrice()` method that is shared by both the nodes and the leaves. Each node in the tree can have children or not.

  The client can get the price of the any box via the `getPrice()` method. If the client asks the price to the large container box, 
  the large container box class will retrieve the price of each child recursively and determine the final price. If the client asks the price a box without subboxes, then that box class will return its price.
* **Decorator**: is used to extend existing classes without using inheritance. For example we have a set of classes like ``Coffee``, ``CoffeeWithoutCoffeine``, ``Mocca``. We want a flexible structure that allows us to add some extra variations to each coffee type like ``Milk``, ``Cream`` and ``Foam``. For this purpose we can define a common interface ``IComponent`` for all classes and a ``Decorator`` class that has a reference to ``IComponent``. Finally to each coffee type we can add a single variation like foam but also add a foam variation that also includes cream. 
* **Proxy**: it is about a ``ProxyClass`` that replicates the interface of a ``Class1`` class. Both ``ProxyClass`` and ``Class1`` derive from ``IProxy``. ``ProxyClass`` acts a substition for ``Class1``. This can be useful for example when we want to do some actions before or after accessing ``Class1``. Some kind of actions could be logging, control access, caching. 

  If a client wants to use ``Class1``, it actually uses ``ProxyClass`` and ``ProxyClass`` references ``Class1``.
* **Facade**: it is used when we have a complex system, for example a large set of objects, and we want to hide that complexity. For this purpose we can create a `Facade` class that exposes a user friendly interface and internally interacts with that complex system. In this way the user can use the `Facade` class to interact with the complex system. 
* **Flyweight**: is also known as *cache*. It is used to reduce the number of objects created. It also tries to reduce the memory footprint by sharing common information between objects rather than saving each piece of common data in each instance. The idea of the Flyweight pattern is to take data changing seldom and put it an extra common class. 
</details>


<details>
<summary>What are the main <b>behavioral</b> design patterns? When are they used?</summary>

The **behavioral** design patterns define how objects communicate with each other.

The main behavioral patterns are:

* **Strategy**: a real-world example of use of the strategy method is the sorting algorithm where the comparison algorithm is a custom piece of code. 
* **Observer**: is used when a ``Class1`` wants to be notified when ``Class2`` changes. ``Class2`` has the ``register`` and ``unregister`` methods so that clients like ``Class1`` can register in order to be notified when ``Class2`` changes.
* **Visitor**: is used when having a set of different objects and we want to apply some new functionality to each object without changing the class codes. The idea of the pattern is to create a `Visitor` class that implements a new functionality for each class member that we have. Each object in our set will implement the `IVisitable` interface.

  This method should be used when the types of different object are well known, i.e. no new types are planned. Indeed if we have a new object type, we also have to edit all the visitor classes.
* **Template**: is used when we have a function `myMethod()` that calls several subfunctions (`func1(), func2()...`) and we want to be able to customize the subfunctions. The solution is to create an abstract class `Template` in which ``myMethod()`` calls `func1(), func2()...` and at the same time `func1(), func2()....` are virtual methods that must be overwritten in the class deriving from `Template`.
* **Command**:  it represents an action as an object, i.e. it is an object that represents a verb. It decouples performing the action from the client that is issuing the command. Common scenarios of use are delayed execution, logging, do/undo.
* **Memento**: is used when we want to save the state of an object so that it can be restored later. The memento pattern uses three classes:
  * `Originator`: is the state whose states we want to save.
  * `Memento`: contains the state of an object to be restored.
  * `CareTaker`: keeps track of multiple instances of `Memento`.
  
* **State**: is used when an object changes its behavior based on its internal state.
  One way to achieve that is to have a set of if-else blocks depending on an internal variable. The solution proposed by the State pattern is to create a concrete class for each state. All state classes derive from an `IState`. For example for a `MobilePhone`, we could have  `SilentState`, `SoundState` and `VibrationState`.

* **Iterator**: we have an `Iterator` which is used to access the elements of a collection sequentially without exposing the 
underlying details.

* **Chain of responsability**: it lets you pass requests along a chain of handlers. Each handler can decide  either to process the request or to pass it to the next handler in the chain. A real-world analogy is that you buy a piece of hardware and you need technical support. You give the request to the call center. The operator might know how to help, in not the request would be passed to the second level support and finally to the engineering team if needed. Each actor decides either to process the request or to pass it to the next actor.

* **Mediator**: it lets you reduce the chaotic dependencies between objects. A real-world analogy are the pilots of aircrafts that
approach or depart the airport. Rather than communicating with each other, they all speak with the air traffic controller who 
decides the landing priorities. If all pilots would communicated with each other, it would be pretty messy as each pilot would need
to know all other aircrafts in the neighborhood.     
</details>


<details>
<summary>Which pattern is used when we need to decouple an abstraction from its implementation?</summary>

When we want to decouple an abstraction from its implementation so that they can vary independently we use the **Bridge** pattern.
</details>

<details>
<summary>When can we use the <b>Prototype</b> pattern?</summary>

The **Prototype** pattern is a creational pattern that creates a copy of an existing object. It can make sense to use the
Prototype pattern when
* the costs of creating a new object are higher and / or
* we need a similar object to the one we already have.
</details>


<details>
<summary>Which design pattern is helpful when we want to add a new functionality to an existing object?</summary>

We can use the **Decorator** pattern as it allows us to add a new functionality to an existing object without changing the structure
of the object itself.
</details>

<details>
<summary>What is a main disadvantage of the <b>Facade</b> design pattern?</summary>

One risk of using the **Facade** design pattern is that the **Facade** class could reference many classes so being internally complex and hard to maintain.
</details>

<details>
<summary>What is the difference between the <b>Composite</b> and <b>Decorator</b> patterns?</summary>

The **Composite** and **Decorator** patterns both deal with a tree-like object structure. Their purpose is different.

The **Composite** pattern is used when we want to deal with a tree-like object structure and treat leaves and nodes in the same way by an interface.

The **Decorator** pattern is used when we want to expand an existing class without using inheritance.
</details>


<details>
<summary>What is the difference between the <b>Adapter</b> and the <b>Proxy</b> patterns?</summary>

**Adapter** and **Proxy** patterns are similar in the sense that they are an intermediate class between a client and a final class.
They purpose is different: **Adapter** wants to adapt the interface of the final class so it can be that it implements only those methods that are needed to adjust the interface. By contrast, **Proxy** offers a perfect replication of the interface of the final class, and, as a result, the Proxy class implements all public methods of the final class.
</details>

<details>
<summary>What is the <b>MVC</b> pattern?</summary>

MVC means **model-view-controller**. It is a pattern that divides the code into three logic units to increase the code maintenability:
* **model**: it contains the data logic. For example it interacts with the database.
* **view**: it is what is visible to the user.
* **controller**: it handles the user interaction and updates the view and model as appropriate. It can request data to the model

Notice that the model and the view never interact with each other.

Let's make an example of the events needed to display some data requested by the user. What happens is
1. The controller receives a request from the user
2. The controller sends a request to the model to retrieve data from the database
3. The model sends the retrieved data to the controller
4. The controller sends the retrieved data to the view.
5. The view sends the presentation data as html to the controller
6. The controller sends the presentation data to the user
</details>


<details>
<summary>What are the differences between the <b>MVVM</b> and the <b>MVC</b> patterns?</summary>

Some differences between the MVVM and MVC patterns are:

* **Event handling**: in MVC the events come from the controller, in MVVM events come from the UI. 
</details>
