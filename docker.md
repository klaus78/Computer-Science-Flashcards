## Docker 

<details>
<summary>What is Docker?</summary>

Docker is an open-source platform that automates the deployment, scaling, and management of applications by packaging them into lightweight, portable containers.
</details>


<details>
<summary>What are the core components of Docker?</summary>

Core Components:

* **Dockerfile**: A text file containing instructions to build a container image.

* **Image**: A read-only template used to create containers.

* **Registry**: A storage and distribution system for images, such as Docker Hub.
</details>

<details>
<summary>On what technologies is Docker based?</summary>

Docker heavily relies on features that are directly built into the Linux kernel: **namespaces** for isolation and **control groups (cgroups)** for resource management.

* **Namespaces**: Namespaces wrap a system resource in an abstraction that makes the processes inside the namespace believe they have their own isolated instance of that resource.
* **CGroups**: While namespaces control what a process can see, cgroups control how much of a resource that process (or group of processes) can use.
</details>

<details>
<summary>What is the difference between Docker containers and Virtual Machines?</summary>

Unlike traditional virtual machines (VMs) that require a heavy guest operating system for every instance, Docker containers share the host machine's operating system kernel. This makes them significantly faster, lighter, and more resource-efficient.
</details>

<details>
<summary>What is the history of Docker?</summary>

The history of Docker spans from its origins as an internal tool at a struggling startup to a technology that completely revolutionized software development and cloud computing.

* **Origins as dotCloud (2008–2013)**: Docker started as dotCloud, a Platform-as-a-Service (PaaS) company founded in France in 2008 by Solomon Hykes, Sebastien Pahl, and Kamel Founadi, later moving to the United States after joining the Y Combinator incubator in 2010. dotCloud allowed developers to host applications by wrapping them in underlying Linux container technology (specifically LXC) to keep them isolated.

* **The Pivot and Public Launch (2013)**: While dotCloud as a PaaS struggled to compete with industry giants, the underlying container engine they built to manage applications internally was recognized as revolutionary. In March 2013, Solomon Hykes publicly unveiled Docker at a PyCon conference. The company open-sourced the technology, shifting its entire focus to the container project. Later that year, dotCloud officially changed its corporate name to Docker, Inc.

* **Explosive Growth and Standardization (2014–2015)**: Docker made complex Linux kernel features (like namespaces and cgroups) accessible to average developers through a simple command-line interface and user-friendly engine. Its popularity exploded across the software industry. To ensure the technology remained open and universal, Docker helped found the Open Container Initiative (OCI) in 2015, establishing open industry standards for container formats and runtimes.

* **Ecosystem Expansion and Enterprise Shift (2016–Present)**: Over the years, Docker expanded its tooling to include orchestration and management ecosystems (like Docker Compose and enterprise integrations). In 2019, the company sold its enterprise business to Mirantis to refocus on developer tooling and workflows.

Today, Docker is an indispensable pillar of modern software engineering, serving as the foundational building block for cloud-native applications, microservices, and automated CI/CD deployment pipelines.

</details>

<details>
<summary>Is there Docker native for Windows?</summary>

Because Docker relies heavily on core Linux kernel features (like **namespaces** and **cgroups**), Linux containers cannot run natively on the Windows kernel. However, Docker provides a seamless official application for Windows called **Docker Desktop** that bridges this gap.

Docker Desktop for Windows runs a lightweight Linux environment behind the scenes.  It uses WSL 2 (Windows Subsystem for Linux) or Hyper-V. WSL 2 is the recommended default backend because it spins up an optimized, lightweight Linux micro-VM that integrates closely with Windows, offering fast performance and low resource overhead.

</details>
