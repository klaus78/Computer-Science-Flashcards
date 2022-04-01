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
<summary>ANS</summary>
<div>
 When using uniform prior, we assign equal weights everywhere, on all possible values of the $\theta$. The implication is that the likelihood equivalently weighted by some constants. Being constant, we could be ignored from our MAP equation, as it will not contribute to the maximization.

  See details [here](https://wiseodd.github.io/techblog/2017/01/01/mle-vs-map/)
</div>
</details>

<details>
  <summary markdown="span">This is the summary text, click me to expand</summary>

  This is the detailed text.

  We can still use markdown, but we need to take the additional step of using the `parse_block_html` option as described in the [Mix HTML + Markdown Markup section](#mix-html--markdown-markup).

  You can learn more about expected usage of this approach in the [GitLab UI docs](https://gitlab-org.gitlab.io/gitlab-ui/?path=/story/base-collapse--default) though the solution we use above is specific to usage in markdown.
</details>