## Design patterns

<details>
<summary>What are the three types of design patterns from the gang-of-four book?</summary>

The three types of design patterns from the gang-of-four book are

* **Creational patterns**: are pattern for object instantiation.
* **Structural patterns**: are patterns defining the structure and relationships among objects.
* **Behavioral patterns**: are patterns about how objects interact and communicate at runtime.

</details>


<details>
<summary>What are the main creational design patterns? When are they used?</summary>

**Creational** design patterns are patterns responsible for the creation of objects.

The main **creational** design patterns are 

* **Abstract factory** is used when we need to create families of related objects. For example we want to create instances
of bank account (normal account or stock count) and identity card (personal id or passport). 
* **Factory** is used when we want to create different flavors of a similar class. For example assume we have the abstract `CreatePizza` class and we create the concrete classes ``CreatePizzaMargherita`` and `CreatePizzaQuattroStagioni`.
* **Builder**: is used when we have a complex object whose creation requires a number of intermediate steps. 
* **Prototype** is used when we want to create a deep-copy of an existing object.

</details>

<details>
<summary>What are the main structural patterns and when are they used?</summary>

**Structural** design patterns define how the objects are structures and organized.

The main structural patterns are:
* **Adapter**: is used when two objects with mismatching interfaces want to communicate. The interface of one of the objects is adapted to the other interface so that the communication is possible.
* **Bridge**: this patterns shows that composition is more flexible than inheritance. This pattern is used to make changes to different aspects of a system independent of one another.

  Suppose that we have a product and a delivery service. If we set the delivery service type inside a product class and we create anew delivery service, we also need to create a new product class with that new delivery service.

  A more flexible solution is that product class references an abstract class of delivery service. In this way I can add a new delivery service without having to create a new product class. 

* **Composite**: is used when we have a tree-like set of objects. For example we could have a large container box that contains smaller fridge boxes and those fridge boxes contain food boxes. This is a tree structure. We create an interface ``IComposite``
with the `getPrice()` method that is shared by both the nodes and the leaves. Each node in the tree can have children or not.

  The client can get the price of the any box via the `getPrice()` method. If the client asks the price to the large container box, 
  the large container box class will retrieve the price of each child recursively and determine the final price. If the client asks the price a box without subboxes, then that box class will return its price.
* **Decorator**: is used to extend existing classing without using inheritance. For example we have a set of classes like Coffee, CoffeeWithoutCoffeine, Mocca. We want a flexible structure that allows us to add some extra variations to each coffee type like milk, cream and foam. For this purpose we can define a common structure ``IComponent`` for all classes and a ``Decorator`` class that has a reference to ``IComponent``. Finally to each coffee type we can add a single variation like foam but also add a foam variation that also includes cream. 
* **Proxy**: it adds a ``proxyclass`` that controls the access to a ``class1``. This can be useful for example when we want to do some actions before or after accessing ``class1``. Some kind of actions could be logging, control access, caching.
* **Facade**: it is used when we have a complex system, for example a large set of objects, and we want to hide that complexity. For this purpose we can create a `Facade` class that exposes a user friendly interface and internally interacts with that complex system. In this way the user can use the `Facade` class to interact with the complex system. 
* **Flyweight**: is also known as *cache*. It is used to reduce the number of objects created. It also tries to reduce the memory footprint by sharing common information between objects rather than saving each piece of common data in each instance. The idea of the Flyweight pattern is to take data changing seldom and put it an extra common class. 

</details>


<details>
<summary>What are the main behavioral design patterns and when are they used?</summary>

The **behavioral** design patterns define how objects communicate with each other.

The main behavioral patterns are:

* **Strategy**: a real-world example of use of the strategy method is the sorting algorithm where the comparison algorithm is a custom piece of code. 
* **Observer**: 
* **Visitor**: is used when have have a set of different objects and we want to apply some new functionality to each object without changing the class codes. The idea of the pattern is to create a `Visitor` class that implements a new functionality for each class member that we have. Each object in our set will implement the `IVisitable` interface. 

  This method should be used when the types of different object is knows, i.e. no new types are planned. Indeed if we have a new object type, we also have to edit all the visitor classes.
* **Template**: is used when we have a function `myMethod()` that calls several subfunctions (`func1(), func2()...`) and we want to be able to customize the subfunctions. The solution is to create an abstract class `Template` in which ``myMethod()`` calls `func1(), func2()...` and at the same time `func1(), func2()....` are virtual methods that must be overwritten in the class deriving from `Template`.

</details>

<details>
<summary>What is a main disadvantage of the Facade design pattern?</summary>

One risk of using the **Facade** design pattern is that the **Facade** class could reference many classes so being internally complex and hard to maintain.

</details>

<details>
<summary>What is the difference between the Composite and Decorator patterns?</summary>

The **Composite** and **Decorator** patterns both deal with a tree-like object structure. Their purpose is different.

The **Composite** pattern is used when we want to deal with a tree-like object structure and treat leaves and nodes in the same way by an interface.

The **Decorator** pattern is used when we want to expand an existing class without using inheritance.
</details>


<details>
<summary>What is the difference between the Adapter and the Proxy patterns?</summary>

**Adapter** and **Proxy** patterns are similar in the sense that they are an intermediate class between a client and a final class.
They purpose is different: **Adapter** wants to adapt the interface of the final class so it can be that it implements only those methods that are needed to adjust the interface. By contrast, **Proxy** offers a perfect replication of the interface of the final class, and, as a result, the Proxy class implements all public methods of the final class.
</details>

<details>
<summary>What is the MVC pattern?</summary>

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
<summary>What are the differences between the MVVM and the MVC patterns?</summary>

Some differences between the MVVM and MVC patterns are:

* **Event handling**: in MVC the events come from the controller, in MVVM events come from the UI. 

</details>