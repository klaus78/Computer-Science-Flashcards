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

The main **creational** design patterns are 

* **Abstract factory** is used when you need to create families of related objects. For example you want to create instances
of bank account (normal account or stock count) and identity card (personal id or passport). 
* **Factory** is used when you want to create different flavors of a similar class. For example assume you have the abstract `CreatePizza` class and you create the concrete classes ``CreatePizzaMargherita`` and `CreatePizzaQuattroStagioni`.
* **Builder**: is used when you have a complex object that requires a number of intermediate steps. 
* **Prototype** is used when you want to create a deep-copy of an existing object.

</details>