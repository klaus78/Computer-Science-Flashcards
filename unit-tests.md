## Unit tests

<details>
<summary>What are unit tests?</summary>
**Unit tests* are tests that checks if a single module works fine. The single module is tested without external dependencies.
</details>

<details>
<summary>What are integration tests?</summary>
**Integration tests* are tests for checking if different modules can work together. 
</details>


<details>
<summary>What are functional tests?</summary>
**Functional tests* are tests that check if an application functionality works fine. Functional tests are done on the complete application.
</details>

<details>
<summary>What are regression tests?</summary>

**Regression** testing is a type of tests that verify if the code changes do not impact existing code.
</details>

<details>
<summary>What are a double tests? How many types of double tests are there?</summary>

**Test doubles** are classes that replicate external components that could be required for a unit test, like a database or a network connection.

There are three types of test double:
* **Fake**: fake class simulating the real class. The code is optimized for testing
* **Stub**: returns a pre-defined data
* **Mock**: record interactions during test. For example it can test count how many times a method of a class was called.

</details>


<details>
<summary>What is a stub?</summary>

A **stub** is a fake object that returns a fixed value.

</details>

<details>
<summary>What is a mock? Can you make an example of it?</summary>

A **mock** is a smarter stub. A mock says if the tests passed or failed. It does so by verifying whether the object under test called the fake object as expected (i.e. the proper methods were called).

</details>




