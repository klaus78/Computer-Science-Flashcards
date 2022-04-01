## Object oriented programming

<details>
<summary>What are the SOLID principles?</summary>

The **SOLID** principles are the following five principles:

* The Single Responsibility Principle
* The Open-Closed Principle
* The Liskov Substitution Principle
* The Interface Segregation Principle
* The Dependency Inversion Principle

**Single Responsibility Principle (SRP):**  a class should do one thing and therefore it should have only a single reason to change. For example you have a `Person` class with methods `setAge(int age)` and `print()`. The `print()` method actually violates the SRP because it contains the print logic of the `Person`. To solve this issue you can create a new class `PrintPerson` which is only responsible for printing the person information.

**Open-Closed Principle (OCP):** classes should be open for extension and closed to modification. This means it should be possible to add a new functionality to a class without changing its existing code.

For example given a `Person` class with methods `saveToFile` and `saveToDatabase`, you could create an interface with method `save(Person p)`, then two classes `SavePersonToFile` and `SavePersonToDatabase` that implement the interface above.

**Liskov Substitution Principle (LSP):** it should be possible to substitute a base class with a child class and we should have the same behavior. This is equivalent to saying that a child class should expand a base class, not restrict it. This is the basic principle of inheritance.

One example of violation of the Liskov principle is when you have a `Square` class that derives from a `Rectangle` class. Because the `Square` class has the constraint that width and height must be equal, it actually restricts the `Rectangle` class and this can lead to unexpected behaviors.

**Interface Segregation Principle (ISP):** when you have one interface with two different task, consider creating two different interfaces instead. In general The principle states that many specific interfaces are better than one general-purpose interface. You should not be forced to implement a function that you do no need.

**Dependency Inversion Principle (DIP):** a class should depend on abstractions and interfaces rather than concrete classes and functions. 

For example if you have a `Car` class that contains an instance of the `Engine` class. This means that if we add a new engine type, say Diesel engine, we need to modify the `Car` class. It would be better to have a reference to a `IEngine` interface instead. In this way the `Car` class would be decoupled from the type of `Engine`.
</details>

<details>
<summary>What the the four core concepts of object oriented programming?</summary>
The four core concepts of object oriented programming are:

* **Inheritance:** inheritance means that a child class can inherit the features of a base class and add new features.
* **Polymorphism:** polymorphism means "appearing in different forms". For example a method in a base class can be overriden in a child class. As a result we have two different forms of that method. Another example of polymorphism is that we can have the same function with different types of parameters.
* **Abstraction:** abstraction is a concept in which the code implementation is hidden away from the user. For example you can have a `Car` class implementing the `IStart` interface with the `start()` method. As users of the class we only care about `Car` implementing the `start()` method and not about any internal variable.  
* **Encapsulation:** encapsulation is a concept that refers to encapsulating some data inside a class by making it private and that data cannot be accessed from outside that class. 
</details>

<details>
<summary>What are the differences between method overloading and method overriding?</summary>
The differences between method overloading and method overriding are:

* **method overloading** is when you have a method with the same name and different parameters, for example you have
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
<summary>What is runtime polymorphism</summary>

**Runtime polymorphism** is a process in which a call to an overridden method is resolved at runtime rather than at compile time.
Runtime polymorphism involves that a child class overrides a method of its parent class. 
</details> 

<details>
<summary>What are some differences between an interface and an abstract class?</summary>

Some differences between an interface and an abstract class are:

* **Methods**: an interface can only have abstract methods while an abstract class can also have methods with a body.

* **Visibility**: all methods in an interface are public by default. An abstract class can also have private methods.

</details> 
