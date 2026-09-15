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

<details>
<summary>In what use cases is Docker recommended?</summary>

Docker is recommended for scenarios where consistency, isolation, and portability across different computing environments are critical. 

- **Local Development and Testing**: Eliminates the "it works on my machine" problem by bundling code, runtimes, and dependencies into containers that precisely mirror production setups.  
- **Microservices Architectures**: Allows individual services to be packaged, deployed, scaled, and updated independently without affecting the rest of the application.  
- **CI/CD (Continuous Integration and Continuous Deployment)**: Ensures that code builds, automated tests, and deployment pipelines run in identical, repeatable environments from development to production.  Cloud-Native and Multi-Cloud Deployments: Simplifies moving applications seamlessly across different cloud providers (AWS, Azure, Google Cloud) or hybrid infrastructures without vendor lock-in.  
- **AI and Machine Learning Workloads**: Packages complex ML frameworks, model weights, and specific library dependencies (like CUDA drivers or Python packages) into portable containers for reproducible training and inference.
- **Dependency Sandboxing and Tool Testing**: Enables developers to spin up temporary services (such as a Redis cache or PostgreSQL database) or test new CLI tools safely without cluttering the host operating system.  
- **Legacy Application Modernization**: Encapsulates older monolithic applications and their legacy dependencies to make them easier to run and manage on modern infrastructure without a complete rewrite.

</details>


<details>
<summary>On what use cases is Docker not recommended?</summary>

These are the most important use cases in which the use of Docker is not recommended:

* **Heavy Desktop GUI Applications**: Running graphical user interface applications inside Docker requires complex workarounds like X11 forwarding or VNC, resulting in input lag, rendering issues, and cumbersome audio/video setups compared to native installations.

* **Cross-Architecture Production Workloads**: Executing heavy container images compiled for a different CPU architecture (such as running linux/amd64 images on linux/arm64 hosts) relies on emulation layers like QEMU, which introduces severe performance penalties.

* **Ultra-Low Latency and High-Performance Computing (HPC)**: Workloads requiring direct bare-metal hardware access, specialized network interfaces, or absolute maximum throughput can suffer from the slight virtualization overhead of network bridging and storage abstraction layers.

* **Forcing Monolithic "All-in-One" Containers**: Bundling multiple unrelated background services, cron daemons, and application servers into a single container violates the core design principle of "one process per container," making debugging, logging, and scaling extremely difficult.

* **Simple Static Content Hosting**: Deploying basic HTML, CSS, and JavaScript websites via Docker adds unnecessary steps—such as writing Dockerfiles, building images, and managing container registries—when static hosting providers or content delivery networks offer zero-config alternatives.

* **Standalone Stateful Databases Without Expertise**: While databases run fine in containers, deploying production-grade databases on a single Docker host without automated backup systems, proper volume management, or orchestration tools risks data corruption and difficult recovery processes.
</details>

<details>
<summary>On what use cases is Docker not recommended?</summary>

These are the most important use cases in which the use of Docker is not recommended:

* **Heavy Desktop GUI Applications**: Running graphical user interface applications inside Docker requires complex workarounds like X11 forwarding or VNC, resulting in input lag, rendering issues, and cumbersome audio/video setups compared to native installations.

* **Cross-Architecture Production Workloads**: Executing heavy container images compiled for a different CPU architecture (such as running linux/amd64 images on linux/arm64 hosts) relies on emulation layers like QEMU, which introduces severe performance penalties.

* **Ultra-Low Latency and High-Performance Computing (HPC)**: Workloads requiring direct bare-metal hardware access, specialized network interfaces, or absolute maximum throughput can suffer from the slight virtualization overhead of network bridging and storage abstraction layers.

* **Forcing Monolithic "All-in-One" Containers**: Bundling multiple unrelated background services, cron daemons, and application servers into a single container violates the core design principle of "one process per container," making debugging, logging, and scaling extremely difficult.

* **Simple Static Content Hosting**: Deploying basic HTML, CSS, and JavaScript websites via Docker adds unnecessary steps—such as writing Dockerfiles, building images, and managing container registries—when static hosting providers or content delivery networks offer zero-config alternatives.

* **Standalone Stateful Databases Without Expertise**: While databases run fine in containers, deploying production-grade databases on a single Docker host without automated backup systems, proper volume management, or orchestration tools risks data corruption and difficult recovery processes.

</details>

<details>
<summary>What is the role of the Docker Daemon (dockerd)?</summary>

**Docker Daemod** is the background service running on the host machine that manages Docker objects, including images, containers, networks, and volumes, by listening for requests from the Docker client API.

</details>