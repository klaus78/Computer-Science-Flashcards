## Cybersecurity

<details>
<summary>What is cybersecurity?</summary>

**Cybersecurity** is the practice of protecting systems, networks, and data from digital attacks, unauthorized access, or damage
</details>

<details>
<summary>What are the main goals of cybersecurity?</summary>

The **main goals** of cybersecurity are defined by the CIA triad:
* **C**onfidentiality: ensuring only authorized users can access data
* **I**ntegrity: ensuring data is accurate and unaltered
* **A**vailability: ensuring systems and data are accessible when needed
</details>

<details>
<summary>What are common types of cyberattacks?</summary>

**Examples of cyberattacks** include phishing, malware, ransomware, SQL injection, and denial‑of‑service (DoS) attacks.
</details>

<details>
<summary>What is phishing?</summary>

**Phishing** is a social engineering attack where attackers impersonate trusted entities to trick users into revealing sensitive information.
</details>

<details>
<summary>What is malware?</summary>

**Malware** is malicious software designed to damage, disrupt, or gain unauthorized access to systems. Examples include viruses, worms, trojans, and spyware.
</details>

<details>
<summary>What is a firewall?</summary>

A **firewall** is a security device or software that monitors and filters incoming and outgoing network traffic based on predefined security rules.
</details>

<details>
<summary>What is encryption?</summary>

**Encryption** is the process of converting readable data into an unreadable format to protect it from unauthorized access. Only someone with the correct decryption key can read it.
</details>

<details>
<summary>What is the difference between vulnerability, threat, and risk?</summary>

* **Vulnerability**: a weakness in a system

* **Threat**: something that can exploit a vulnerability

* **Risk**: the potential impact when a threat exploits a vulnerability
</details>

### Missing Function Level Access Control

<details>
<summary>What is Missing Function Level Access Control?</summary>

**Missing Function Level Access Control (MFLAC)** is a critical security vulnerability where an application fails to properly 
verify a user's authorization before allowing them to access specific functions or URLs.
</details>

<details>
<summary>How does an attacker typically exploit the MFLAC vulnerability?</summary>
Attackers often use a method called URL Forced Browsing. They guess or discover administrative URLs and attempt to access them directly.

Example: A regular user changes their profile URL from example.com/user/settings to example.com/admin/delete_user. If the server processes the delete request without checking if the user is an admin, the system is vulnerable.
</details>

<details>
<summary>Does "Security by Obscurity" protect against MFLAC?</summary>
No. Hiding a button in the UI (User Interface) does not secure the function. If the underlying API or server-side function remains unprotected, an attacker can find the endpoint using browser developer tools, proxy logs, or brute-force "fuzzing."
</details>

<details>
<summary>What are the common impacts of an MFLAC vulnerability?</summary>
No. Hiding a button in the UI (User Interface) does not secure the function. If the underlying API or server-side function remains unprotected, an attacker can find the endpoint using browser developer tools, proxy logs, or brute-force "fuzzing."
</details>

### XML External Entities (XXE Injection)

<details>
<summary>What is an XXE injection, and how does it work?</summary>
An XML External Entity (XXE) injection is a type of attack against an application that parses XML input. It occurs when XML input containing a reference to an external entity is processed by a weakly configured XML parser.

Attackers can use this to define a custom entity within a Document Type Definition (DTD) that points to a sensitive URI (like a local file or an internal server). When the parser "expands" this entity, it includes the contents of that URI in the application's output or processing logic.
</details>

<details>
<summary>What is the most effective way to prevent XXE?</summary>
The gold standard for prevention of XXL is disabling the processing of external entities and DTDs entirely in your XML parser. Since most modern applications don't actually need these legacy features, turning them off removes the attack surface without affecting functionality.
</details>

<details>
<summary>What are the potential impacts of a successful XXE attack?</summary>

XXE is dangerous because it provides a "Swiss Army Knife" of exploitation. The three primary impacts are:

- Data Retrieval: Reading sensitive files from the server (e.g., /etc/passwd or configuration files containing credentials).

- Server-Side Request Forgery (SSRF): Forcing the server to make HTTP requests to internal systems or metadata services (like AWS/Azure metadata endpoints).

- Denial of Service (DoS): Using the "Billion Laughs" attack, where nested entities expand exponentially, crashing the server's memory.
</details>


<details>
<summary>Why is the Document Type Definition (DTD) central to XXE?</summary>

The DTD is where the "rules" of an XML document are defined. XXE specifically abuses the !ENTITY tag within the DTD. While entities were originally designed to act as shortcuts for repetitive text, the ability to define an EXTERNAL entity allows the XML to reach outside of its own document to fetch data from the file system or the internet.

Note: Even if your application doesn't use DTDs for its logic, an attacker can still submit a document that contains a DTD, and a poorly configured parser will process it anyway.
</details>


