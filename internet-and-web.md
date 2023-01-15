## Web concepts and programming
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

## Web apis

<details>
<summary>
What are SOAP and REST? What do these terms mean?
</summary>

SOAP and REST are ways to make web services, i.e. are ways to form the HTTP request and response.

SOAP = simple object access protocol

REST = representational state transfer

</details>

<details>
<summary>
What are the difference between SOAP and REST?
</summary>    

SOAP
* each SOAP API has the POST method just by default but is not used
* each API using SOAP uses a WSDL (web services description language).
* WSDL is an xml format that describes the API and what you can do with it
* In the HTTP body the XML format is used
       
REST
* rest = representational state transfer
* while in SOAP you pass the POST method which is not actually used, in REST you pass the GET,PUT,POST,DELETE methods and they are used
* it is said to be stateless ie it does not depend on the state of server
</details>

<details>
<summary>
What does it mean that the REST APIs are stateless?
</summary>
The REST apis are **stateless**  in the sense that the answers of the server do not depend on previous session information, In other words, each answer of the server is independent of any previous api call from the client.
</details>