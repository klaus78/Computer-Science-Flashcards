## Object oriented programming

<details>
<summary>What are the SOLID principles?</summary>

The **SOLID** principles are the following five principles:

* The Single Responsibility Principle
* The Open-Closed Principle
* The Liskov Substitution Principle
* The Interface Segregation Principle
* The Dependency Inversion Principle

**Single Responsibility Principle (SRP):**  a class should do one thing and therefore it should have only a single reason to change. For example we have a `Person` class with methods `setAge(int age)` and `print()`. The `print()` method actually violates the SRP because it contains the print logic of the `Person`. To solve this issue we can create a new class `PrintPerson` which is only responsible for printing the person information.

**Open-Closed Principle (OCP):** classes should be open for extension and closed to modification. This means it should be possible to add a new functionality to a class without changing its existing code.

For example given a `Person` class with methods `saveToFile` and `saveToDatabase`, we could create an interface with method `save(Person p)`, then two classes `SavePersonToFile` and `SavePersonToDatabase` that implement the interface above.

**Liskov Substitution Principle (LSP):** it should be possible to substitute a base class with a child class and we should have the same behavior. This is equivalent to saying that a child class should expand a base class, not restrict it. This is the basic principle of inheritance.

One example of violation of the Liskov principle is when we have a `Square` class that derives from a `Rectangle` class. Because the `Square` class has the constraint that width and height must be equal, it actually restricts the `Rectangle` class and this can lead to unexpected behaviors.

**Interface Segregation Principle (ISP):** when we have one interface with two different task, consider creating two different interfaces instead. In general The principle states that many specific interfaces are better than one general-purpose interface. We should not be forced to implement a function that we do no need.

**Dependency Inversion Principle (DIP):** a class should depend on abstractions and interfaces rather than concrete classes and functions. 

For example if we have a `Car` class that contains an instance of the `Engine` class. This means that if we add a new engine type, say Diesel engine, we need to modify the `Car` class. It would be better to have a reference to a `IEngine` interface instead. In this way the `Car` class would be decoupled from the type of `Engine`.
</details>

<details>
<summary>What the the four core concepts of object oriented programming?</summary>
The four core concepts of object oriented programming are:

* **Inheritance:** inheritance means that a child class can inherit the features of a base class and add new features. Inheritance is a mechanism for reusing code.
* **Polymorphism:** polymorphism means "appearing in different forms". For example a method in a base class can be overriden in a child class. As a result we have two different forms of that method. Another example of polymorphism is that we can have the same function with different types of parameters.
* **Abstraction:** abstraction is a concept in which the code implementation is hidden away from the user. For example we can have a `Car` class implementing the `IStart` interface with the `start()` method. As users of the class we only care about `Car` implementing the `start()` method and not about any internal variable.  
* **Encapsulation:** encapsulation is a concept that refers to encapsulating some data inside a class by making it private and that data cannot be accessed from outside that class. 
</details>

<details>
<summary>What are the differences between method overloading and method overriding?</summary>
The differences between method overloading and method overriding are:

* **method overloading** is when we have a method with the same name and different parameters within the same class. For example we have
```Csharp
class myClass {
    int add(int a, int b) {return a+b;}
    int add(int a, int b, int c) {return a+b+c;}
}
```
Method overload is also called compile time polymorphism.

* **method overriding:** involves a child class deriving from a base class and that child class overrides a method of the base class. In this case the parameters must be the same. For example
```Csharp
class myBase{
    virtual public int increment(int n) { return n + 1; }
}

class myChild : myBase
{
    override public int increment(int n) { return n + 2; }
}
```
Method overriding is also called runtime polymorphism.
</details> 

<details>
<summary>What is runtime polymorphism? What is compile time polymorphism?</summary>

**Runtime polymorphism** is a process in which a call to an overridden method is resolved at runtime rather than at compile time.
Runtime polymorphism involves that a child class overrides a method of its parent class. 

**Compile time polymorphism** is when we have a class with a method with the same name but different parameters. In this case depending on the types of parameters passed, the compiler knows what version of the method it is to be called.
</details> 

<details>
<summary>What are some differences between an interface and an abstract class?</summary>

Some differences between an interface and an abstract class are:

* **Methods**: an interface can only have abstract methods while an abstract class can also have methods with a body.

* **Visibility**: all methods in an interface are public by default. An abstract class can also have private methods.

</details> 

<details>
<summary>What is the difference between the visibility of private, protected and public methods?</summary>

* **Private methods** are visibile only within the class.

* **Protected methods** are are visible within the class and also within the child classes.

* **Public methods** are visible everywhere.

</details>

<details>
<summary>What is a static method?</summary>

A **static method** is a method that can be called without creating an instance of a class.

</details>

<details>
<summary>What is an abstract method?</summary>

An **abstract method** is a method that has only a signature and has no body. It can be declared only in an abstract class.

</details>

<details>
<summary>What is inversion of control (IOC)?</summary>

**Inversion of control (IOC)** is a generic concept that involves providing any kind of callback
instead of acting ourselves directly. We can also say that we delegate a functionality to an external component 
which gives us back the desired result with a callback. In this way we pass *control* to an external component.
That external component could be a framework or a library. 

For example rather than having `class1` creating an instance of `class2`, an instance of `class2` is passed to the constructor of `class1`. In this way `class1` is not responsible for the creation of `class2`. 

</details>


 <details>
<summary>What is dependency injection (DI)?</summary>

**Dependency injection (DI)** is a subtype of inversion of control focused on class instances. 

Let us suppose we have `class1` that references `class2` and `class3`. With a dependency injection framework, `class1` does not need to
create the instances of `class2` and `class3`. These are created by the DI framework and injected into `class1` with one of the following techniques: 

* constructor injection
* property injection
* method injection 

</details>

<details>
<summary>When is composition to be prefered over inheritance?</summary>

At first consider that 
* **Composition** is a **has a** relationship, like a car has an engine.
* **Inheritance** is a **is a** relationship, like a car is a vehicle. Remember that inheritance
  is a more strong relationship and it should respect the Liskov substitution principle (a parent class should be completely replacable
  by a child class).

A pragmatic way to determine if you need composition or inheritance is

* Does TypeB want to expose the complete interface (all public methods no less) of TypeA such that TypeB can be used where TypeA is expected? Indicates Inheritance. E.g. A Cessna biplane will expose the complete interface of an airplane, if not more. So that makes it fit to derive from Airplane.
* Does TypeB want only some/part of the behavior exposed by TypeA? Indicates need for Composition. E.g. A Bird may need only the fly behavior of an Airplane. In this case, it makes sense to extract it out as an interface / class / both and make it a member of both classes.


Another, very pragmatic reason, to prefer composition over inheritance has to do with your domain model, and mapping it to a relational database. It's really hard to map inheritance to the SQL model (you end up with all sorts of hacky workarounds, like creating columns that aren't always used, using views, etc). Some ORMLs try to deal with this, but it always gets complicated quickly. Composition can be easily modeled through a foreign-key relationship between two tables, but inheritance is much harder.

</details>