# COMP315 Revision Outline

## 1. Data Centres

### A. Data Centre Tour
*   **External & Internal Views:**
    *   AWS Data Centre: Large, secure facilities.
    *   Google Data Centre: Rows of server racks, cooling infrastructure, cabling.
*   **Key Components (Visuals):**
    *   **Server Rack:** Standardized frame for mounting servers and other equipment.
    *   **Server:** Individual computer unit providing compute resources.
    *   **Network Switch:** Device connecting multiple devices on a network.
*   **Cooling:**
    *   **Server Cooling:** Internal fans and airflow management within a server.
    *   **Rack Cooling:** Methods like underfloor air distribution to cool entire racks.
    *   **Other Approaches:**
        *   Locating data centres in cool climates.
        *   Underwater data centres (e.g., Microsoft's Project Natick) for natural cooling.

### B. Data Centre Hardware Components
*   **Commodity Hardware:**
    *   Definition: Servers built from relatively inexpensive, readily available ("off-the-shelf") components.
    *   Characteristics: Higher spec than typical desktop PCs but uses similar, standardized parts for easy replacement and cost-effectiveness.
*   **Compute Resources:**
    *   Server Components: CPUs, RAM, hard disks, network cards. Typically headless (no monitor, keyboard, mouse).
    *   **Top of Rack Switch:**
        *   Connects all servers within the same rack.
        *   Connects the rack to the broader data centre network.
    *   Storage: Hard drives can be local to servers or network-accessible.
*   **Local Networks vs. The Internet:**
    *   **Local Area Networks (LANs):**
        *   Scope: Small geographic area (e.g., building, campus).
        *   Ownership: Typically a single organization.
        *   Examples: Office networks, home networks.
    *   **The Internet:**
        *   Scope: Global network of interconnected networks.
        *   Ownership: No single entity.
*   **Network Interface Cards (NICs):**
    *   Function: Allow hardware to connect to a network.
    *   Also known as: Network interfaces, network adaptors, network cards.
    *   **MAC Addresses:**
        *   Unique Media Access Control address assigned to each NIC.
        *   "Burned-in address" (historically), now usually in firmware.
        *   Format: Six pairs of hexadecimal digits (e.g., `00:1A:2B:3C:4D:5E`).
            *   First 3 pairs: Organizationally Unique Identifier (OUI) - manufacturer.
            *   Last 3 pairs: NIC-Specific Identifier - device-specific.
*   **Network Switches:**
    *   Function: Connect devices *within* a single computer network.
*   **Routers:**
    *   Function: Connect *multiple* networks together and direct traffic between them.
*   **Firewalls:**
    *   Function: Network security devices at the boundary, monitor and filter traffic based on rules.

### C. Multiple Choice Questions (Key Concepts Highlighted)
*   Commodity hardware is chosen for cost-effectiveness, availability, and standard components.
*   Top-of-rack switches serve as local switching points for servers in a rack and connect them to the broader data centre network.

## 2. Server Software
### A. Operating Systems
*   **Operating Systems for Cloud Servers:**
    *   Function: Manage hardware/software resources, provide an interface for programs.
        *   Resource allocation (CPU, memory, I/O).
        *   File system management.
        *   User interface (GUI/CLI).
    *   Cloud Servers primarily use **Linux**.
*   **Linux:**
    *   Free, open-source family of OS based on the Linux kernel.
    *   Created by Linus Torvalds.
    *   Dominant in cloud computing.
    *   **Distributions:** Various versions (e.g., RHEL, Ubuntu, CentOS). RHEL is typical for cloud servers.
    *   **Linux Kernel:**
        *   Core of the OS; manages hardware, provides essential services.
        *   Handles process management, memory management, device drivers.
*   **Kernel Space vs. User Space:**
    *   **Kernel Space:** Where the kernel operates; has complete hardware access; protected memory area.
    *   **User Space:** Where user applications run; limited hardware access; must communicate with kernel for resources.
    *   (Diagram: Applications (User) -> Kernel -> Hardware (Kernel Space components)).
*   **The Root User:**
    *   Special account with highest privileges (still operates in user space).
    *   Can modify system settings, manage accounts.
    *   Risky if used improperly; use regular user accounts for daily tasks.

### B. Virtual Machines
*   **Virtualisation:**
    *   Creating virtual versions of physical components (servers, storage, networks).
    *   **Virtual Machines (VMs):** Software emulations of an entire physical server.
    *   **Hypervisor:** Software layer enabling VM creation and management on physical hardware.
*   **Type 1 vs. Type 2 Hypervisors:**
    *   **Type 1 (Bare-metal):**
        *   Runs directly on host hardware.
        *   High performance.
        *   Examples: VMware ESXi, Microsoft Hyper-V.
        *   Tech Stack: Hardware -> Hypervisor -> VMs -> Applications.
    *   **Type 2 (Hosted):**
        *   Runs on a host OS.
        *   Easier setup.
        *   Examples: VMware Workstation, Oracle VirtualBox.
*   **Benefits of Virtualisation:**
    *   Efficiency: Maximizes resource utilization.
    *   Cost Savings: Reduces need for physical hardware.
    *   Flexibility: Eases deployment and management.
    *   Isolation: Provides secure, isolated environments (though SELinux offers more robust isolation).

### C. Multiple Choice Questions (Key Concepts Highlighted)
*   Linux kernel provides essential services by managing hardware resources via system calls.
*   Type 1 hypervisors (bare-metal) typically have lower overhead than Type 2 hypervisors.

## 3. HTML and CSS
### A. HTML (Hyper Text Markup Language)
*   **Core Concepts:**
    *   Standard markup language for web page structure.
    *   **Hypertext:** Links to other documents/text.
    *   **Markup:** System for annotating text.
*   **Basic Document Structure:**
    *   `<html>`, `<head>` (contains metadata, title, links to CSS/JS), `<body>` (contains visible content).
    *   Common elements: `<title>`, `<h1>` to `<h6>`, `<p>`, `<a>`, `<img>`, `<ul>`, `<ol>`, `<li>`.
*   **Tags and Elements:**
    *   **Tags:** Enclosed in angle brackets (e.g., `<p>`, `</p>`).
    *   **Elements:** Defined by tags, represent parts of a webpage. Can be nested.
*   **HTML Element Attributes:**
    *   Provide additional information about elements.
    *   `class`: For CSS styling and JS selection (multiple elements can share a class).
    *   `id`: Unique identifier for an element, for CSS and JS.
    *   `style`: For inline CSS.
    *   `href` (for `<a>`): Specifies URL of the link.
    *   `src` (for `<img>`, `<script>`): Specifies source of the resource.

### B. CSS (Cascading Style Sheets)
*   **Core Concepts:**
    *   Describes the look, formatting, and layout of HTML documents.
    *   Capabilities: Font, color, size, spacing, layout (columns), animations.
*   **Adding CSS to HTML:**
    *   External CSS: `<link rel="stylesheet" type="text/css" href="styles.css">` in `<head>`.
    *   Internal CSS: `<style>` tags in `<head>`.
    *   Inline CSS: `style` attribute on an HTML element.
*   **Selectors:**
    *   Target HTML elements for styling (e.g., element type `p`, class `.my-class`, ID `#my-id`).
*   **Properties and Values:**
    *   e.g., `color: blue;`, `font-size: 16px;`, `background-color: lightgray;`.

### C. The DOM (Document Object Model)
*   **Definition:** Programming interface for HTML (and XML) documents.
*   **Structure:** Represents the document as a tree of objects (nodes).
*   **Manipulation:**
    *   Initially populated from HTML.
    *   JavaScript can dynamically access and modify the DOM's content, structure, and style.
    *   This allows for interactive web pages.
*   **DOM Example Diagram:** Shows hierarchical structure (document -> html -> head/body -> further elements).

### D. Tailwind CSS
*   **Utility-First CSS Framework:**
    *   Provides pre-defined utility classes to style HTML elements directly in the markup.
    *   Reduces the need to write custom CSS.
    *   Example: `<button class="bg-blue-500 text-white font-bold py-2 px-4 rounded">`.
*   **Key Classes (Examples from slides):**
    *   `bg-blue-900` (background color), `text-center` (text alignment), `text-white` (text color), `p-4` (padding), `my-4` (margin y-axis), `text-3xl` (text size), `font-bold`, `underline`.
*   **Integration:** Can be included via CDN or as part of a build process.

### E. JavaScript for Web Pages (Brief Introduction)
*   **Role:** Adds interactivity and dynamic behavior.
*   **Capabilities:**
    *   Respond to user events (clicks, key presses).
    *   Manipulate the DOM.
    *   Make network requests (AJAX).
*   **Example (from slides):**
    *   Using `window.onload`, `document.querySelector()`, `addEventListener()` to make buttons interactive (show alerts).

### F. Multiple Choice Questions (Key Concepts Highlighted)
*   DOM is a dynamic tree-like structure generated from HTML, manipulable by JavaScript.
*   `<head>` contains metadata, title, links; `<body>` contains rendered content.
*   Tailwind CSS `class` attribute assigns utility classes for direct styling.

## 4. JavaScript
### A. JavaScript Basics
*   **Running JavaScript:**
    *   Browser Console: For testing and execution.
    *   Node.js: Command-line runtime (V8 engine).
        *   Install from `nodejs.org`.
        *   Run interactive shell with `node`.
*   **Primitive Types:**
    *   `Undefined`: Variable declared but not assigned.
    *   `Null`: Intentional absence of an object value.
    *   `Boolean`: `true`, `false`.
    *   `Number`: Integers and floating-point numbers.
    *   `String`: Textual data.
    *   `Symbol` (ES6): Unique, immutable identifiers.
    *   `BigInt` (ES2020): Arbitrary-length integers (e.g., `1234n`).
    *   Note: Functions are objects.
*   **Undefined vs. Null:**
    *   `undefined`: Default for uninitialized variables, function return without explicit return, non-existent properties.
    *   `null`: Explicitly assigned to indicate "no value" or "no object".
*   **Expressions vs. Statements:**
    *   **Expression:** Code unit that resolves to a value (e.g., `2+2`, `x > 5`).
    *   **Statement:** Performs an action (e.g., variable declaration, loop, conditional). Can contain expressions.
*   **Variable Declaration (`let`, `const`, `var`):**
    *   `let`: Block-scoped, can be reassigned but not re-declared in the same scope.
    *   `const`: Block-scoped, cannot be reassigned or re-declared (must be initialized).
    *   `var`: Function-scoped (or global if outside function), can be re-declared and reassigned. Avoid due to hoisting and scope confusion.
*   **Scope:**
    *   **Function Scope:** `var` variables are scoped to the function they are declared in.
    *   **Block Scope:** `let` and `const` variables are scoped to the block (`{...}`) they are declared in.
*   **Truthiness and Falsiness:**
    *   Values behave as `true` (truthy) or `false` (falsy) in boolean contexts.
    *   **Falsy values:** `false`, `0`, `-0`, `0n`, `""` (empty string), `null`, `undefined`, `NaN`.
    *   All other values are **truthy** (including `{}`, `[]`, `"0"`, `"false"`).
*   **Equality Operators:**
    *   `==` (Loose Equality): Performs type coercion. (e.g., `1 == '1'` is true).
    *   `===` (Strict Equality): Does not perform type coercion. (e.g., `1 === '1'` is false). **Recommended.**
*   **Template Literals (Backticks `` ` ``):**
    *   Allow embedded expressions: `` `Hello, ${name}!` ``.
    *   Support multi-line strings.

### B. Compound Data Types
*   **Arrays:**
    *   Ordered collections of elements.
    *   Creation: `let arr = [1, 'two', true];`.
    *   Access: `arr[0]`.
    *   Methods:
        *   Modifying: `push()`, `pop()`, `shift()`, `unshift()`, `splice()`.
        *   Accessing/Copying: `slice()`, `concat()`.
*   **Objects:**
    *   Unordered collections of key-value pairs (properties).
    *   Creation (Literal): `let obj = { name: "Alice", age: 30 };`.
    *   Access: `obj.name` or `obj['name']`.
    *   Modification/Addition: `obj.age = 31; obj.city = "New York";`.
    *   **Methods and `this`:**
        *   Methods are functions stored as object properties.
        *   `this` keyword refers to the object the method is called on (context-dependent).
            *   In strict mode, `this` in a regular function is `undefined`.
    *   **Object Literals vs. Object Constructors:**
        *   Literal: `{...}`.
        *   Constructor: `new Object()`.
    *   **Standard Object Methods:** `Object.keys()`, `Object.entries()`, `Object.assign()`.
    *   **Functions are Objects:** Can have properties and methods.
    *   **Object Destructuring:** `const { name, age } = user;`.
    *   **Spread Operator (`...`) for Objects:**
        *   Shallow copy: `const newObj = { ...oldObj };`.
        *   Merge objects: `const mergedObj = { ...obj1, ...obj2 };`.
*   **Prototype Chains (Prototypal Inheritance):**
    *   Objects inherit properties and methods from their prototype.
    *   `[[Prototype]]` (internal property) links to the prototype object.
    *   `Object.create(proto)` creates an object with a specified prototype.
    *   `__proto__` (legacy, avoid direct use).
    *   Methods are typically on the prototype, properties on the instance.

### C. Control Flow
*   **Conditionals:**
    *   `if...else if...else`.
    *   `switch` statement.
    *   Ternary operator: `condition ? val1 : val2`.
*   **Loops:**
    *   `for` loop: `for (let i = 0; i < limit; i++)`.
    *   `for...of` loop (ES6): Iterates over values of iterable objects (arrays, strings).
    *   `for...in` loop: Iterates over enumerable properties of an object (keys).
    *   `while` loop.
    *   `do...while` loop.

### D. Functions
*   **Declaration & Expressions:**
    *   Function Declaration: `function myFunction() {}`.
    *   Function Expression: `const myFunction = function() {};`.
    *   Arrow Functions (ES6): `const myFunction = () => {};` or `(params) => expression`.
*   **Parameters:**
    *   **Rest Parameters (`...`):** Collects remaining arguments into an array. `function sum(...numbers) {}`.
*   **`this` Keyword in Functions:** (Covered in Objects section).
*   **Strict Mode (`"use strict";`):**
    *   Enables stricter error checking, changes behavior of `this`.

### E. Classes (ES6)
*   Syntactic sugar over prototypal inheritance.
*   **Definition:** `class MyClass { constructor() {} method() {} }`.
*   **Constructor:** Special method for creating and initializing objects.
*   **Inheritance:** `class ChildClass extends ParentClass { constructor() { super(); } }`.
    *   `super()` calls the parent class constructor.

### F. JSON (JavaScript Object Notation)
*   Lightweight data-interchange format.
*   Syntax:
    *   Objects: `{"key": "value"}`. Keys must be double-quoted strings.
    *   Arrays: `[1, "two", true]`.
    *   Primitives: Strings (double-quoted), numbers, booleans (`true`/`false`), `null`.
*   **Serialization/Deserialization:**
    *   `JSON.stringify(object)`: JS object to JSON string.
    *   `JSON.parse(jsonString)`: JSON string to JS object.

### G. YAML (YAML Ain’t Markup Language)
*   Human-readable data serialization language, often used for configuration.
*   Syntax:
    *   Key-value pairs: `key: value`.
    *   Lists (Sequences): `- item1\n- item2`.
    *   Dictionaries (Mappings): Indentation defines structure.
    *   Primitives: Strings (often unquoted), numbers, booleans (e.g., `true`, `yes`, `false`, `no`), `null` (or `~`).
    *   Indentation is significant.
    *   Optional `---` (start) and `...` (end).

### H. Multiple Choice Questions (Key Concepts Highlighted)
*   Truthy gotchas: `"0"` is truthy, `[]` and `{}` are truthy.
*   `null` vs. `undefined`: Both falsy, `null` is an explicit assignment of "no value", `undefined` means a variable has not been assigned a value. `null !== undefined`.
*   `var`, `let`, `const`: Scoping differences (function vs. block), re-assignment/re-declaration rules.

## 5. Security
### A. Vulnerabilities and the Zero-Day Problem
*   **Inherent Insecurity of Computers:** Absolute security is unattainable due to complexity, flaws, and human error.
*   **Patch Cycle:** Discovery -> Patch Preparation -> Publication -> Installation.
*   **Zero-Day Vulnerabilities:** Exploits for which no patch is yet available.

### B. Host Defences
*   **Principle of Least Privilege (PoLP):** Grant minimum necessary access.
*   **Sandboxing:** Running programs in restricted environments.
*   **Discretionary Access Control (DAC):** (Default Linux) Permissions based on user executing the program.
    *   File Permissions (`rwx` for owner, group, others; numeric e.g., `755`).
    *   Commands: `chmod`, `sudo`.
*   **Mandatory Access Control (MAC):** (e.g., SELinux) OS enforces system-wide policies set by an administrator.

### C. SELinux (Security-Enhanced Linux)
*   **Introduction:** MAC framework in Linux kernel.
*   **Modes:** Enforcing, Permissive, Disabled.
*   **Labelling System:** Processes, files, ports, etc., have labels. Policies define allowed interactions between labels.
*   **Type Enforcement:** Primary model; labels based on types (e.g., `httpd_t` for Apache process, `httpd_sys_content_t` for web content).
*   **Multi-Category Security (MCS):** Adds categories to labels for finer-grained control between instances of the same type (e.g., different users' data).
*   **Multi Level Security (MLS):** Controls access based on hierarchical data sensitivity levels (e.g., secret, top-secret). Enforces concepts like "no read up, no write down" (Bell-LaPadula like).
*   **Interaction:** Type Enforcement, MCS, and MLS can work together.

## 6. Containers
### A. Introduction to Containers
*   Lightweight alternative to VMs.
*   Encapsulate application and dependencies.
*   Run on host OS kernel, providing process-level isolation.
*   Tools: Docker, PodMan, Kubernetes.

### B. Docker
*   **Images and Containers:** Containers are instances of images.
*   **Dockerfiles:** Text files defining how to build an image (layers).
    *   Instructions: `FROM`, `RUN`, `COPY`, `CMD`, `ENTRYPOINT`, `EXPOSE`.
*   **Docker Layers:** Read-only layers stacked to form an image.
*   **Docker Hub:** Public registry for Docker images.
*   **CLI Commands:** `docker pull`, `docker run`, `docker build`, `docker ps`, `docker stop`, `docker rm`, `docker rmi`.

### C. Containers and the Linux Kernel
*   **Namespaces:** Provide isolation for resources (PID, NET, MNT, UTS, IPC, USER). Each container gets its own set.
*   **Control Groups (cgroups):** Manage and limit resource usage (CPU, memory, I/O) per container.
*   **Union File Systems:** Layered file systems allowing shared read-only base layers and per-container writeable layers.

### D. Orchestration and Kubernetes (Introduction)
*   **Orchestration:** Managing lifecycle of containerized applications at scale (deployment, scaling, self-healing).
*   **Kubernetes (K8s):** Popular open-source container orchestration system.
    *   History: Google (Borg/Omega), CNCF.
    *   Naming: "Helmsman", k8s.
*   **CRI (Container Runtime Interface) & OCI (Open Container Initiative):**
    *   Kubernetes uses CRI for pluggable runtimes (e.g., `containerd`).
    *   OCI defines container image format and runtime specs.
*   **Microservices:** Architectural style facilitated by containers and orchestration.

## 7. Networking
### A. Protocol Stacks
*   **OSI Model (7 Layers):**
    1.  Physical (Bits, signals)
    2.  Data Link (Frames, MAC addresses, Ethernet, switches)
    3.  Network (Packets, IP addresses, routing, routers)
    4.  Transport (Segments/Datagrams, TCP/UDP, ports, reliability, flow control)
    5.  Session (Managing communication sessions)
    6.  Presentation (Data translation, encryption, compression)
    7.  Application (High-level protocols, HTTP, DNS, FTP, SMTP)
*   **TCP/IP Stack (Conceptual Mapping to OSI):**
    *   Application (OSI Layers 5-7)
    *   Transport (OSI Layer 4)
    *   Internet (OSI Layer 3)
    *   Network Access / Physical (OSI Layers 1-2)

### B. Addressing
*   **MAC Address:** Layer 2, physical address of NIC.
*   **IP Address:** Layer 3, logical address for network identification.
    *   IPv4: 32-bit (e.g., `192.168.1.10`).
    *   IPv6: 128-bit.
*   **Port Number:** Layer 4, identifies specific application/service on a host (e.g., `:80` for HTTP).
*   **Domain Name:** Human-readable, resolved to IP by DNS.

### C. Key Protocols by Layer
*   **Layer 2 (Data Link):** Ethernet (frames, MAC addresses, CRC).
*   **Layer 3 (Network):** IP (packets, routing, fragmentation).
*   **Layer 4 (Transport):**
    *   TCP: Reliable, ordered, connection-oriented.
    *   UDP: Unreliable, connectionless, fast.
    *   SSL/TLS: Secure communication (encryption, authentication, integrity).
        *   TLS Handshake: Cipher suite negotiation, certificate exchange (CA), session key generation.
        *   Certificate Authorities (CAs): Issue digital certificates (e.g., Let's Encrypt).
*   **Layer 7 (Application):**
    *   HTTP/HTTPS: Web communication.
        *   HTTP Methods (Verbs): `GET`, `POST`, `PUT`, `DELETE`, `PATCH`.
    *   DNS: Domain Name System.
    *   SMTP: Email sending.
    *   FTP: File transfer.

## 8. Ansible
### A. Core Concepts
*   **Configuration as Code (CaC):** Managing configurations using code.
*   **Agentless Architecture:** No agents on managed nodes; uses SSH.
*   **Idempotency:** Operations can be run multiple times with the same outcome (only changes if needed).
*   **Declarative Language:** Describe desired state, Ansible figures out how to achieve it.

### B. Inventory
*   Defines hosts and groups of hosts.
*   Formats: INI, YAML.
*   Static or Dynamic.
*   Host variables (e.g., `ansible_host`, `ansible_connection`).
*   `group_vars/` and `host_vars/` directories for organizing variables.

### C. Playbooks
*   YAML files defining plays, tasks, and roles.
*   **Plays:** Map hosts/groups to tasks.
    *   `hosts:`, `become: yes` (privilege escalation).
*   **Tasks:** Units of action, call modules.
    *   `name:`, module name (e.g., `ansible.builtin.yum`, `ansible.builtin.service`).
    *   `when:` for conditional execution.
    *   `loop:` for iterating tasks.
    *   `register:` to store task output in a variable.
    *   `debug:` module for printing variable values or messages.
*   **Modules:** Pre-built units of code performing specific actions (e.g., `ping`, `yum`, `service`, `file`, `copy`, `template`, `selinux`, `reboot`, `lineinfile`, `replace`).
*   **Handlers:** Tasks triggered by `notify` directive, run at the end of a play if changes occurred.

### D. Variables and Facts
*   **Variables:** Defined in playbooks, inventory, `vars_files`, `group_vars`, `host_vars`.
    *   Interpolation: `{{ my_variable }}`.
*   **Facts:** System information gathered by Ansible about managed nodes (e.g., `ansible_facts.default_ipv4.address`, `ansible_selinux.status`).
*   **Ansible Vault:** Encrypts files containing sensitive data (e.g., `secret.yml`).
    *   Commands: `ansible-vault create`, `ansible-vault edit`, `ansible-vault encrypt`, `ansible-vault decrypt`.
    *   Running playbooks with vaulted files: `--ask-vault-pass`.
*   **Password Hashing:** `password_hash` filter (e.g., `{{ my_pass | password_hash('sha512') }}`).

### E. Command-Line Tools
*   `ansible`: Ad-hoc commands (e.g., `ansible all -m ping`).
*   `ansible-playbook`: Runs playbooks.
    *   Flags: `-i` (inventory), `-m` (module for `ansible`), `--ask-become-pass` (`-K`), `--ask-vault-pass`, `--tags`.

### F. Everything as Code (EaC) & XaaS
*   **EaC:** Managing all aspects of a software system (infra, config, build, deploy, monitor) as code.
    *   **IaC (Infrastructure as Code):** Provisioning infrastructure with code (e.g., Terraform, Ansible).
    *   **CaC (Configuration as Code):** Managing system configurations with code (e.g., Ansible).
*   **Declarative vs. Imperative:**
    *   Declarative: Define desired state.
    *   Imperative: Define steps to achieve state.
*   **XaaS (Anything as a Service):**
    *   **IaaS:** Infrastructure (VMs, storage, network).
    *   **PaaS:** Platform for building/deploying apps (e.g., Kubernetes).
    *   **SaaS:** Software for end-users (e.g., Gmail).

## 9. Hosting
### A. Website Hosting Overview
*   How websites are made available on the internet.
*   **Web Servers:** Software that hosts and serves web content (HTML, CSS, JS) over HTTP/HTTPS.
    *   Example: Apache, NGINX.
*   **Docker for Hosting:** Used to set up Apache/NGINX instances.

### B. Proxies
*   **Forward Proxy:**
    *   Acts as intermediary between client and internet.
    *   Use Cases: Caching, anonymizing client requests, access control/content filtering.
    *   Example: University intranet proxy.
*   **Reverse Proxy:**
    *   Sits between internet and web servers.
    *   Use Cases: Load balancing, enhancing security (hiding backend IPs), SSL termination, caching static content.
    *   Example: NGINX used as a reverse proxy for Apache.
    *   Example: E-commerce website proxy.
*   **Diagrams:**
    *   Web Servers (Client -> Internet -> Web Servers).
    *   Forward Proxy (Client -> LAN (Forward Proxy) -> Internet -> Web Servers).
    *   Reverse Proxy (Client -> Internet -> Reverse Proxy (Web Server LAN) -> Web Servers).

### C. Apache Web Server
*   Popular open-source web server.
*   **Functionality:**
    *   Handles HTTP(S) requests from clients.
    *   Processes requests (serves static files, executes server-side scripts).
    *   Serves content back to client.
*   **Setting up an HTTP Server with Docker & Apache:**
    *   **HTML Code:** Basic `index.html` example.
    *   **Dockerfile for Apache HTTP Server:**
        *   `FROM httpd:latest` (official Apache image).
        *   `COPY index.html /usr/local/apache2/htdocs/` (default document root).
        *   `EXPOSE 80` (default HTTP port).
    *   **Building Docker Image:** `docker build -t apache-image .`.
    *   **Running Container:** `docker run --name apache-container -p 8081:80 apache-image`.
        *   `-p 8081:80`: Maps host port 8081 to container port 80.
    *   Accessing: `http://localhost:8081`.
*   **Apache Configuration (`httpd.conf`):**
    *   Accessing: `docker exec -it apache-container /bin/bash`, then navigate to `/usr/local/apache2/conf/`. Or `docker cp apache-container:/usr/local/apache2/conf/httpd.conf .`.
    *   `DocumentRoot`: Specifies directory from which Apache serves files (e.g., `/usr/local/apache2/htdocs`).
*   **Adding HTTPS to Apache:**
    *   **Self-Signed Certificates (for development):**
        *   Generated with `openssl`.
        *   Command: `openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out selfsigned.crt -subj "/C=UK/ST=Merseyside/L=Liverpool/O=MyOrg/CN=www.example.com"`.
        *   `-subj` fields: C (Country), ST (State), L (Locality), O (Organization), CN (Common Name - domain).
    *   **Apache SSL Configuration (`httpd-ssl.conf`):**
        *   `Listen 443`
        *   `<VirtualHost *:443>`
        *   `SSLEngine on`
        *   `SSLCertificateFile "/usr/local/apache2/conf/selfsigned.crt"`
        *   `SSLCertificateKeyFile "/usr/local/apache2/conf/private.key"`
        *   `DocumentRoot "/usr/local/apache2/htdocs/"`
        *   `ServerName www.example.com`
    *   **Updating Dockerfile for HTTPS:**
        *   `COPY selfsigned.crt ...`, `COPY private.key ...`, `COPY httpd-ssl.conf ...`.
        *   Enable SSL modules in `httpd.conf` using `sed` (e.g., uncomment `LoadModule ssl_module modules/mod_ssl.so`).
        *   Include `httpd-ssl.conf` in main `httpd.conf` (e.g., `RUN echo 'Include conf/extra/httpd-ssl.conf' >> /usr/local/apache2/conf/httpd.conf`).
        *   `EXPOSE 80 443`.
    *   **Building and Running HTTPS Docker Image:**
        *   Build: `docker build -t apache-ssl-image .`.
        *   Run: `docker run --name apache-ssl-container -p 8081:80 -p 8082:443 apache-ssl-image`.
    *   **Certificate Warning:** Browsers warn about self-signed certificates. For production, use CA-signed certificates.

### D. NGINX as a Reverse Proxy
*   **Reverse Proxy Function:** Receives HTTP/HTTPS requests, forwards to backend server(s).
*   **Docker Networking:** Create a Docker network for NGINX and Apache to communicate: `docker network create web-net`.
*   **NGINX Configuration (`nginx.conf`):**
    *   `upstream apache-server { server apache-container:80; }` (defines backend).
    *   `server { listen 80; location / { proxy_pass http://apache-server; } }` (listens on port 80, forwards to upstream).
*   **Dockerfile for NGINX:**
    *   `FROM nginx:latest`.
    *   `RUN rm /etc/nginx/conf.d/default.conf`.
    *   `COPY nginx.conf /etc/nginx/conf.d/`.
    *   `EXPOSE 80`.
*   **Building and Running NGINX Container:**
    *   Build: `docker build -f Nginx.Dockerfile -t nginx-reverse-proxy .`.
    *   Run Apache (on `web-net`): `docker run -d --name apache-container --network web-net apache-image`.
    *   Run NGINX (on `web-net`, exposing port): `docker run -d --name nginx-proxy --network web-net -p 8083:80 nginx-reverse-proxy`.
    *   Access via NGINX: `http://localhost:8083`.

## 10. Storage
### A. Storage Solutions
*   **Local Server Storage:**
    *   Hard drives on the server.
    *   Fast access times.
    *   Used for OS data, frequently accessed persistent data.
    *   Not ideal for cloud: If server/service fails, data on that server is inaccessible to a new host.
    *   Data centre storage often separated from compute servers.
*   **Network Attached Storage (NAS):**
    *   Devices with multiple hard drives (often in RAID).
    *   Connect to network via NICs, accessed as shared drives.
    *   Disadvantage: Single point of failure (if NAS device fails).
    *   **RAID (Redundant Array of Independent Disks):** Combines multiple physical disks into logical units for redundancy and/or performance.
*   **Storage Area Network (SAN):**
    *   Specialized networks for storing data (disk arrays, switches, servers).
    *   Fault-tolerant (data replicated).
    *   Recognized by OS as locally attached drives.
    *   Easily extended.
    *   Typically fibre optic.
    *   Separate network: Unaffected by compute network traffic, ensuring SAN performance.

### B. Databases
*   **Relational Databases (RDBMS):**
    *   Store data in tables (relations).
    *   Each table has rows (tuples/records) and columns (attributes).
    *   Unique key (primary key) identifies each record.
    *   Tables linked by keys (foreign keys).
    *   **SQL (Structured Query Language):** Used for querying.
    *   Examples: MySQL, PostgreSQL.
    *   **Join Operation:** Combines rows from two or more tables based on a related column.
*   **Graph Databases:**
    *   Store data in **nodes** (entities) and **edges** (relationships).
    *   Nodes and edges can have attributes (properties).
    *   Suitable for highly connected data.
    *   Applications in E-commerce:
        *   Personalized Recommendations.
        *   Fraud Detection.
        *   Supply Chain Analysis.
        *   Customer 360 View.
*   **NoSQL Databases:**
    *   "Not only SQL" or "non-SQL".
    *   Non-relational, handle unstructured/semi-structured data.
    *   Examples:
        *   Document Databases (MongoDB): Store data in JSON-like documents.
        *   Key-Value Stores.
        *   Column-Family Stores (Cassandra).
        *   Graph Databases (Neo4j) are also often categorized under NoSQL.

### C. Neo4j (Graph Database Example)
*   Popular graph database.
*   **Usage Options:**
    *   Neo4j Aura: Managed cloud service.
    *   Neo4j Desktop: Local application.
    *   Docker: `docker run -p7474:7474 -p7687:7687 -e NEO4J_AUTH=neo4j/<password> neo4j`.
*   **Cypher Query Language:**
    *   Query language for Neo4j.
    *   **Creating Nodes:**
        *   `CREATE (ee:Person {name: 'Emil', from: 'Sweden', kloutScore: 99})`
        *   `(variable:Label {property: value})`
    *   **Finding Nodes:**
        *   `MATCH (ee:Person) WHERE ee.name = 'Emil' RETURN ee;`
        *   `MATCH` specifies a pattern.
        *   `WHERE` filters results.
        *   `RETURN` specifies what to output.
    *   **Creating Relationships (Edges):**
        *   `CREATE (js:Person {name: 'Johan'})-[:KNOWS {since: 2001}]->(ee)`
        *   `-[variable:RELATIONSHIP_TYPE {property:value}]->`
    *   **MATCH Patterns for Relationships:**
        *   `MATCH (emil:Person)-[:KNOWS]-(friends) WHERE emil.name = 'Emil' RETURN emil, friends;`
        *   `-[:KNOWS]-` matches KNOWS relationship in either direction.
        *   `(friends)` captures the nodes Emil knows.
*   **Neo4j Browser:** Web interface for interacting with Neo4j (running queries, visualizing graph).

## 11. TypeScript
### A. TypeScript Basics
*   **Introduction:**
    *   Superset of JavaScript, adds static type checking.
    *   Compiles to plain JavaScript.
    *   Helps catch errors at compile time, improves code maintainability for large projects.
    *   Evolution of JavaScript: From a "toy language" for simple browser interactivity to a language for complex applications, leading to features like classes and static typing (via TypeScript).
*   **Variable Declarations and Type Inference:**
    *   **Explicit Type Annotations:** `let a: number = 1;`, `let b: string = 'hello';`.
    *   **Type Inference:** TypeScript can infer types if not explicitly annotated: `let a = 1; // a is inferred as number`.
*   **Compiling TypeScript:**
    *   `tsc hello_world.ts` compiles to `hello_world.js`.
    *   Resulting JS can be run with Node.js: `node hello_world.js`.
*   **Static Type Checking Benefits:** Catches type errors at compile time.
    *   Example: `function squareOf(n: number) { return n * n; } squareOf('z'); // Error TS2345`.

### B. Primitive and Special Types
*   **`any`:** Catch-all type, opts out of type checking. Use sparingly.
*   **`unknown`:** Safer alternative to `any`. Must perform type checks before operating on `unknown` values.
*   **`boolean` and Literal Boolean Types:**
    *   `let a: boolean = true;`.
    *   Literal types: `let b: true = true;` (b can only be `true`). `let c: false = false;`.
*   **`number` and Literal Number Types:**
    *   `let a: number = 1234;`.
    *   Literal types: `const c: 5678 = 5678;`.
*   **`bigint` and Literal BigInt Types:**
    *   For very large integers: `let a: bigint = 1234n;`.
*   **`string` and Literal String Types:**
    *   `let a: string = "hello";`.
    *   Literal types: `let b: "world" = "world";`.
*   **`symbol`:** Represents unique, immutable values. `let a: symbol = Symbol('a');`.
*   **`null` and `undefined`:** Have their own types `null` and `undefined`.

### C. Object Types
*   **Defining Object Shapes:**
    *   `let a: { b: number }; a = { b: 1 };`.
    *   TypeScript enforces the shape.
*   **Optional Properties:** `c?: string;` (c is optional).
*   **Index Signatures:** For objects with dynamic keys.
    *   `[key: string]: number;` (any string key must have a number value).
    *   `[key: number]: boolean;` (any numeric key must have a boolean value).
*   **`readonly` Properties:** Cannot be reassigned after initialization. `readonly firstName: string;`.

### D. Type Aliases, Unions, and Intersections
*   **Type Aliases:** Create new names for types.
    *   `type Age = number;`.
    *   `type Person = { name: string; age: Age; };`.
*   **Union Types (`|`):** Variable can be one of several types.
    *   `type CatOrDog = Cat | Dog;`.
    *   `let id: string | number;`.
*   **Intersection Types (`&`):** Combines multiple types into one.
    *   `type CatAndDog = Cat & Dog;` (object must have all properties of Cat AND Dog).

### E. Arrays and Tuples
*   **Arrays:**
    *   Typed arrays: `let a: number[] = [1, 2, 3];` or `let b: Array<string> = ['a', 'b'];`.
    *   Type inference: `let c = ['red']; // c is string[]`. If empty `let d = []; // d is any[]`.
*   **Tuples:** Arrays with a fixed number of elements of known types.
    *   `let a: [string, number] = ['hello', 10];`.
    *   Optional elements: `[string, number?];`.
    *   Rest elements: `[string, ...number[]];` (at least one string, followed by any number of numbers).

### F. Functions
*   **Parameter Types and Return Types:**
    *   `function greet(name: string): string { return 'Hello ' + name; }`.
    *   Return type can often be inferred.
*   **Optional Parameters:** `function log(message: string, userId?: string) {}`.
*   **Default Parameters:** `function log(message: string, userId = 'guest') {}`.
*   **Rest Parameters:** `function sum(...numbers: number[]): number {}`.
*   **`this` in Functions:** (Context-dependent, be mindful of arrow functions vs. regular functions for `this` binding).
*   **Function Type Aliases:**
    *   `type LogFunction = (message: string, userId?: string) => void;`.
*   **Generic Functions (and Types):**
    *   Create reusable components that can work over a variety of types.
    *   `function map<T, U>(array: T[], f: (item: T) => U): U[] { ... }`.
    *   `T` and `U` are type parameters (placeholders).
    *   Type alias for generic function: `type Filter = <T>(array: T[], f: (item: T) => boolean) => T[];`.
    *   Binding generics:
        *   `Filter1`: `<T>` on right of assignment (instantiated at call time).
        *   `Filter2<T>`: `<T>` on left (type fixed when `Filter2` is defined/used).

### G. Classes
*   **Definition:** `class ChessPiece { ... }`.
*   **Constructors:** `constructor(private color: Color, file: FileVal, rank: RankVal) { ... }`.
    *   Parameter properties (e.g., `private color: Color`) automatically create and initialize member variables.
*   **Access Modifiers:**
    *   `public` (default): Accessible from anywhere.
    *   `private`: Accessible only within the class.
    *   `protected`: Accessible within the class and its subclasses.
*   **Methods:** Functions defined within a class.
*   **Inheritance:** `class King extends Piece { ... }`.
    *   `super()` to call parent constructor.
*   **Abstract Classes and Methods:**
    *   `abstract class Piece { abstract canMoveTo(position: Position): boolean; ... }`.
    *   Abstract classes cannot be instantiated directly.
    *   Abstract methods must be implemented by concrete subclasses.
*   **Static Methods and Properties:** Belong to the class itself, not instances. `static makePieces() {}`.
*   **Structural Typing:** TypeScript checks type compatibility based on shape/structure, not explicit inheritance or nominal typing.
    *   If class `Zebra` and class `Poodle` both have a `trot()` method, they can be used interchangeably where an object with a `trot()` method is expected.
*   **Generics for Classes:** `class MyMap<K, V> { ... }`.

### H. Interfaces
*   Another way to define the shape of objects (similar to type aliases for objects).
*   `interface Sushi { calories: number; salty: boolean; tasty: boolean; }`.
*   **Interface Inheritance:** `interface Feline extends Animal { meow(): void; }`.
*   **Declaration Merging:** Multiple interface declarations with the same name are merged. (Type aliases do not merge).
*   **Implementing Interfaces:** Classes can implement interfaces.
    *   `class Cat implements Animal, Feline { ... }`.
    *   Class must provide implementations for all members of the implemented interfaces.

## 12. Kubernetes
### A. Kubernetes Fundamentals
*   **Introduction:** Open-source container orchestration system.
*   **Minikube:** Tool to run a local single-node Kubernetes cluster.
    *   Installation requires a driver (hypervisor or containerization solution like Docker, KVM2, VirtualBox).
    *   Commands: `minikube start`, `minikube status`, `minikube ssh`, `minikube ip`.
*   **kubectl:** Command-line tool to interact with Kubernetes clusters.
    *   Commands: `kubectl get nodes`, `kubectl get pods`, `kubectl describe pod <pod-name>`, `kubectl delete pod <pod-name>`, `kubectl run nginx --image=nginx`, `kubectl get namespaces`.
*   **Cluster Structure:**
    *   **Nodes:** Machines (physical or virtual) that run applications.
        *   **Control Plane Nodes (Master Nodes):** Manage the cluster. Must be Linux.
        *   **Worker Nodes:** Run containerized applications (Pods). Can be Linux or Windows.
    *   **High Availability (HA):** Achieved by replication across multiple nodes and Availability Zones (AZs).
*   **Control Plane Components:**
    *   **API Server:** Frontend for Kubernetes control plane; exposes RESTful API over HTTPS.
    *   **Cluster Store (etcd):** Key-value store holding cluster state and configuration.
    *   **Scheduler:** Assigns Pods to Nodes based on resources and constraints.
    *   **Controllers:** Watch cluster state and work to bring it to desired state (e.g., Deployment Controller, ReplicaSet Controller).
    *   **Controller Manager:** Runs the controllers.
*   **Worker Node Components:**
    *   **Kubelet:** Agent on each node; manages Pod lifecycle, communicates with API server.
    *   **Container Runtime:** Software that runs containers (e.g., `containerd`).
    *   **Kube Proxy:** Manages network rules on nodes (e.g., service IP routing).
*   **Pods:**
    *   Smallest deployable units in Kubernetes.
    *   Hold one or more containers, storage resources, unique network IP, and options.
    *   System pods run in `kube-system` namespace (e.g., `coredns`, `etcd-minikube`, `kube-apiserver-minikube`).
    *   Pause containers: Hold network namespace for other containers in the pod.
*   **Deployments:**
    *   Higher-level concept managing Pods and ReplicaSets.
    *   Declarative updates for Pods (rolling updates, rollbacks).
    *   Ensures a specified number of Pod replicas are running.
    *   Commands: `kubectl create deployment <name> --image=<image>`, `kubectl get deployments`, `kubectl describe deployment <name>`.
*   **Services:**
    *   Abstract way to expose an application running on a set of Pods as a network service.
    *   Provides a stable IP address and DNS name for a deployment.
    *   Types:
        *   `ClusterIP` (default): Exposes service on an internal IP in the cluster.
        *   `NodePort`: Exposes service on each Node’s IP at a static port.
        *   `LoadBalancer`: Exposes service externally using a cloud provider’s load balancer.
        *   `ExternalName`: Maps service to DNS name.
    *   Commands: `kubectl expose deployment <name> --port=<port> --target-port=<container-port> --type=<type>`, `kubectl get services (svc)`.
    *   Accessing via Minikube: `minikube service <service-name>`.
*   **Namespaces:** Virtual clusters within a physical cluster, for resource isolation.
    *   Default namespaces: `default`, `kube-system`, `kube-public`, `kube-node-lease`.

### B. Setting up a Multi-Node Kubernetes Cluster with Ansible
*   **Objective:** One master, two worker nodes (Rocky Linux).
*   **Ansible for Setup:**
    *   Inventory file (`inventory.yml`): Defines master and worker nodes with their IPs.
    *   Ping nodes to check accessibility: `ansible all -i inventory.yml -m ping`.
*   **Pre-requisites & Configuration (on all nodes via Ansible):**
    *   **Disable SELinux:** Kubernetes doesn't support it directly.
        *   Ansible module: `ansible.posix.selinux` with `state: disabled`.
        *   Verify: `sestatus` on nodes.
    *   **Disable Swap:** Historically not supported, can cause issues with Kubelet.
        *   Edit `/etc/fstab` to comment out swap line (Ansible `replace` or `lineinfile` module with regex).
        *   Regex example: `^(\s*)([^#\n]+\s+)(\S+\s+)swap(\s+.*)$` replaced with `# \1\2\3swap\4`.
    *   **Reboot nodes** after these changes.
    *   **Firewall Configuration (firewalld):** Open necessary ports.
        *   Control Plane Ports (TCP): 6443 (API), 2379-2380 (etcd), 10250 (Kubelet), 10257 (controller-manager), 10259 (scheduler).
        *   Worker Node Ports (TCP): 10250 (Kubelet), 10256 (kube-proxy), 30000-32767 (NodePort services).
        *   Calico ports (if used): e.g., TCP 179, UDP 4789.
        *   Ansible module: `ansible.builtin.firewalld`.
    *   **Kernel Modules:** Add `overlay` and `br_netfilter`.
        *   Create `/etc/modules-load.d/k8s.conf` with module names.
        *   Ansible `lineinfile` or `copy`.
    *   **Kernel Parameters (sysctl):** Enable IP forwarding.
        *   Set `net.ipv4.ip_forward = 1` in `/etc/sysctl.d/k8s.conf`.
        *   Apply with `sysctl --system` (Ansible `command` or `sysctl` module, often with a handler).
    *   **Configure Host Names:** Ensure nodes can resolve each other by hostname.
        *   Edit `/etc/hosts` on all nodes.
        *   Ansible `lineinfile` or `template`, using `ansible_facts` like `hostvars[item]['ansible_facts']['default_ipv4']['address']`.
*   **Installation Steps (via Ansible):**
    *   **Install Container Runtime (containerd):**
        *   Install `yum-utils`.
        *   Add Docker repository.
        *   Install `containerd.io`.
        *   Configure containerd: Edit `/etc/containerd/config.toml`, set `SystemdCgroup = true`.
        *   Enable and start `containerd` service.
    *   **Install Kubernetes Packages:** `kubelet`, `kubeadm`, `kubectl`.
        *   Add Kubernetes YUM repository.
        *   Install packages, potentially excluding specific versions if needed (e.g., `disable_excludes=kubernetes` if `exclude` is in repo file).
        *   Enable and start `kubelet` service. (Kubelet will initially be in a crash loop waiting for `kubeadm`).
*   **Initializing the Cluster:**
    *   **Master Node:**
        *   `kubeadm init --control-plane-endpoint=master` (or specific IP/DNS).
        *   Output provides `kubeadm join` command for workers and control-plane nodes.
        *   Create a non-root user (e.g., `kube`), add to `wheel` group for sudo.
        *   Copy Kubernetes admin config to new user's home: `mkdir -p $HOME/.kube`, `sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config`, `sudo chown $(id -u):$(id -g) $HOME/.kube/config`.
    *   **Worker Nodes:**
        *   Run the `kubeadm join` command (from `kubeadm init` output) as root on each worker.
*   **Install Overlay Network (Pod Network Add-on):**
    *   Required for Pod-to-Pod communication across nodes.
    *   Example: Calico.
    *   Apply Calico manifest on master: `kubectl apply -f https://.../calico.yaml`.
    *   Verify pods in `calico-system` namespace.
*   **Checking Cluster Status:**
    *   `kubectl get nodes`: Status should change from `NotReady` to `Ready` after network add-on.
    *   Label worker nodes: `kubectl label node <worker-node-name> node-role.kubernetes.io/worker=worker`.

### C. Advanced Kubernetes Operations
*   **Exposing Services Outside the Cluster (Recap & Detail):**
    *   `NodePort`: Exposes service on each Node's IP at a static port.
    *   `LoadBalancer`: Uses cloud provider's load balancer (preferred for production).
    *   Minikube: `minikube service <service-name>` or `minikube tunnel` for LoadBalancer type.
*   **Scaling Deployments:**
    *   `kubectl scale deployment <deployment-name> --replicas=<number>`.
*   **Updating Deployment Images (Rolling Updates):**
    *   `kubectl set image deployment/<deployment-name> <container-name>=<new-image-tag>`.
    *   Kubernetes replaces old Pods with new ones gradually.
    *   Automatic rollback on failure.
*   **Rolling Back Deployments:**
    *   `kubectl rollout undo deployment/<deployment-name>`.
    *   Check status: `kubectl rollout status deployment/<deployment-name>`.
*   **Resilience:** Kubernetes automatically recreates Pods if they fail or are deleted (if managed by a Deployment/ReplicaSet).
*   **Kubernetes Dashboard:** Web-based UI for managing and monitoring cluster resources.
    *   Access with Minikube: `minikube dashboard`.
*   **Deleting All Resources in a Namespace:** `kubectl delete all --all -n <namespace>` (or current namespace if `-n` omitted).
*   **Manifests (YAML/JSON):**
    *   Declarative way to define Kubernetes resources (Pods, Deployments, Services).
    *   Preferred over imperative `kubectl create/run` commands for complex setups and GitOps.
    *   **Deployment Manifest Example:**
        *   `apiVersion: apps/v1`
        *   `kind: Deployment`
        *   `metadata: { name: k8s-web-hello }`
        *   `spec: { replicas: 5, selector: { matchLabels: { app: k8s-web-hello } }, template: { metadata: { labels: { app: k8s-web-hello } }, spec: { containers: [{ name: k8s-web-hello, image: bstashchuk/k8s-web-hello, ports: [{ containerPort: 3000 }], resources: { limits: { memory: "128Mi", cpu: "250m" } } }] } } }`
    *   **Service Manifest Example:**
        *   `apiVersion: v1`
        *   `kind: Service`
        *   `metadata: { name: k8s-web-hello-service }`
        *   `spec: { type: LoadBalancer, selector: { app: k8s-web-hello }, ports: [{ port: 3000, targetPort: 3000 }] }`
    *   Apply manifest: `kubectl apply -f <filename.yaml>`.
    *   Edit manifest and re-apply to update resources.

### D. Service Mesh with Istio
*   **Service Mesh:** Dedicated infrastructure layer for managing service-to-service communication.
    *   Adds observability, traffic management, security without changing container code.
*   **Istio:** Popular open-source service mesh.
    *   **Components:**
        *   **Data Plane:** Envoy proxies deployed as sidecars alongside each service container in Pods. Handles traffic between services.
        *   **Control Plane (Istiod):** Configures and manages Envoy proxies.
    *   **Features:**
        *   Traffic Management: Routing rules, load balancing, retries, timeouts.
        *   Observability: Detailed telemetry (metrics, logs, traces).
        *   Security: mTLS, authorization policies.
*   **Canary Releases:** Gradually shift traffic to a new version of a service. Istio facilitates fine-grained traffic control for this.
*   **Setting up Istio on Minikube:**
    *   Minikube requirements: At least 6 CPUs, 8GB RAM.
    *   Download Istio: `curl -L https://istio.io/downloadIstio | sh -`. Add `istioctl` to PATH.
    *   Install Istio: `istioctl install`. Creates `istio-system` namespace.
    *   Verify: `kubectl get ns`, `kubectl get pod -n istio-system`.
*   **Deploying Microservices Demo (Online Boutique):**
    *   Clone demo app: `git clone ...microservices-demo.git`.
    *   Apply Kubernetes manifests: `kubectl apply -f kubernetes-manifests.yaml`.
    *   **Enable Istio Sidecar Injection:** Label the target namespace: `kubectl label namespace default istio-injection=enabled`.
    *   Re-deploy application (delete and apply manifests) for sidecars to be injected. Pods will show `2/2` containers ready.
*   **Istio Addons:** For observability (Prometheus, Grafana, Jaeger, Kiali).
    *   Located in Istio download: `samples/addons/`.
    *   Apply: `kubectl apply -f samples/addons`.
    *   Access tools via port-forwarding (e.g., `kubectl port-forward svc/grafana -n istio-system 3000:3000`).
        *   **Grafana:** Visualization of metrics.
        *   **Kiali:** Service mesh observability, configuration, validation (visualizes service graph).
        *   **Prometheus:** Monitoring and alerting toolkit.
        *   **Jaeger:** Distributed tracing.

### E. CI/CD with GitLab and ArgoCD
*   **Continuous Integration (CI):** Developers integrate code into a shared repo frequently; automated builds and tests.
*   **Continuous Delivery/Deployment (CD):** Automatically deliver/deploy code changes to production after CI.
*   **Code Reviews:** Key part of CI/CD; peer review before integration.
*   **DevOps:** Practices combining software development (Dev) and IT operations (Ops).
*   **GitOps:** Using Git as the single source of truth for declarative infrastructure and applications; CI/CD pipelines automate deployments based on Git repo changes.
*   **Git Fundamentals:**
    *   Version control system.
    *   Repositories (local/remote), Branches (feature branches, main/master).
    *   Staging Area: Prepare changes before committing.
    *   Commands: `git clone`, `git add`, `git commit -m "message"`, `git push`, `git pull`, `git fetch`, `git merge`, `git branch`, `git checkout`, `git status`, `git log`, `git diff`, `git stash`, `git revert`, `git reset`.
        *   `git reset`: Rewrites history (use with caution on shared branches).
        *   `git revert`: Creates a new commit to undo changes (safer for shared branches).
*   **GitLab for CI:**
    *   `.gitlab-ci.yml`: Configures CI/CD pipeline in GitLab.
    *   Jobs triggered by commits/pushes.
    *   Example: Build Docker image and push to GitLab Container Registry.
        *   Uses Docker-in-Docker (`image: docker`, `services: - docker:dind`).
        *   Predefined CI/CD variables: `CI_REGISTRY_PASSWORD`, `CI_REGISTRY_USER`, `CI_REGISTRY_IMAGE`.
*   **ArgoCD for CD (GitOps tool):**
    *   Automatically implements changes to Kubernetes cluster based on Git config files.
    *   Cluster configuration stored in a Git repository (single source of truth).
    *   Modifications via Git pushes, not direct `kubectl` commands.
    *   **Installation:**
        *   `kubectl create namespace argocd`.
        *   `kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml`.
    *   **Accessing ArgoCD UI:**
        *   Port-forward service: `kubectl port-forward svc/argocd-server -n argocd 8080:443`.
        *   Get initial admin password: `kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d`.
    *   **Application YAML (`application.yaml`):** Main ArgoCD config file.
        *   Defines source Git repo, path to manifests, destination cluster/namespace, sync policy.
    *   **Deployment & Service YAMLs (in Git repo):** Standard Kubernetes manifests for the application.
    *   ArgoCD monitors Git repo and syncs cluster state to match manifests.

## 13. React
### A. React Fundamentals
*   **Introduction:** Popular JavaScript library/framework for building user interfaces.
*   **Client-Side Framework:** Primarily designed to run in the client's browser. (Next.js extends this).
*   **Components:**
    *   Self-contained, reusable pieces of UI (e.g., button, menu).
    *   Manage their own content, presentation, and behavior.
    *   Build UIs by defining and combining components.
*   **Virtual DOM:**
    *   React uses a virtual representation of the DOM.
    *   Components manipulate the virtual DOM.
    *   React efficiently updates the actual browser DOM based on virtual DOM changes.
*   **Single Page Applications (SPAs):** React can build entire websites as a single page, with content dynamically updated via DOM manipulation.
*   **Thinking in Components:** Breaking down UI into a hierarchy of components.
*   **JSX (JavaScript XML):**
    *   Syntax extension for JavaScript, allows writing HTML-like code within JS.
    *   `App.jsx` is a common main component file.
    *   Example: `const element = <h1>Hello, world!</h1>;`.
    *   Expressions can be embedded: `<h1>Hello, {name}</h1>`.
    *   Attributes similar to HTML, but use camelCase (e.g., `className` instead of `class`).
*   **Web Frameworks Comparison:** React is a leading front-end framework (others: Vue, Angular, Svelte).

### B. Setting Up a React Project
*   **Node.js and npm (Node Package Manager):** Prerequisites.
    *   Node.js: JS runtime.
    *   npm: Package manager for JS libraries.
*   **Creating a React Project with Vite:**
    *   `npm create vite@latest ecommerce-site -- --template react`.
    *   Vite: Fast, modern build tool.
    *   `cd ecommerce-site`, `npm install` (install dependencies).
    *   `npm run dev` (start development server).
*   **Project Structure (Vite):**
    *   `index.html`: Main HTML file (often minimal, with a root div).
    *   `package.json`: Project metadata, dependencies, scripts.
    *   `src/`: Source code.
        *   `main.jsx` (or `.tsx`): Entry point, renders root component.
        *   `App.jsx` (or `.tsx`): Main application component.
    *   `vite.config.js`: Vite configuration.
*   **`package.json` Scripts:**
    *   `dev`: Starts development server.
    *   `build`: Creates production build.
    *   `lint`: Runs linter (e.g., ESLint).

### C. Building a Simple React App
*   **Function Components:** Primary way to define components in modern React.
    *   JavaScript functions that return JSX.
    *   Example: `function Welcome(props) { return <h1>Hello, {props.name}</h1>; }`.
*   **Props (Properties):**
    *   How components receive data from parent components.
    *   Passed as attributes in JSX: `<Welcome name="Sara" />`.
    *   Accessed as an object in the child component (e.g., `props.name`).
    *   Read-only: Child components cannot modify props directly.
    *   Make components reusable and dynamic.
    *   Re-render: If a prop changes, the component re-renders.
*   **Import/Export:**
    *   `export default App;` (exporting a component).
    *   `import ButtonComponent from './ButtonComponent';` (importing).
    *   Named exports/imports: `import { useState } from 'react';`.
*   **Rendering:** Process of turning React code into an actual web page.
    *   Function components return JSX.
    *   React creates virtual DOM, then updates actual DOM.
*   **Adding Tailwind CSS to React (Vite):**
    *   Install: `npm install -D tailwindcss postcss autoprefixer`.
    *   Initialize: `npx tailwindcss init -p`. Creates `tailwind.config.js` and `postcss.config.js`.
    *   Configure `tailwind.config.js`: Add paths to template files in `content` array.
    *   Add Tailwind directives to main CSS file (e.g., `src/index.css`): `@tailwind base; @tailwind components; @tailwind utilities;`.
    *   Use Tailwind classes in JSX: `<div className="bg-blue-500 ...">`.

### D. React Hooks
*   Functions that let you "hook into" React state and lifecycle features from function components.
*   Rules of Hooks: Only call at top level, only from React functions.
*   **`useState` Hook:**
    *   Adds state to function components.
    *   `const [state, setState] = useState(initialState);`.
    *   Returns an array: current state value and a function to update it.
    *   Calling `setState` triggers a re-render.
    *   State updates are asynchronous.
    *   Example: `const [count, setCount] = useState(0); <button onClick={() => setCount(count + 1)}>`.
*   **`useEffect` Hook:**
    *   Performs side effects in function components (e.g., data fetching, subscriptions, manually changing DOM).
    *   `useEffect(() => { /* side effect */ return () => { /* cleanup */ }; }, [dependencyArray]);`.
    *   Callback function: Contains side effect logic. Optional cleanup function returned.
    *   Dependency array: Controls when the effect runs.
        *   Empty array `[]`: Runs once after initial render (and cleanup on unmount).
        *   With variables `[var1, var2]`: Runs after initial render and if any dependency changes.
        *   Omitted: Runs after every render (rarely desired).
    *   Example: Fetching data when component mounts or a prop changes.
*   **`useContext` Hook:** (Mentioned, not detailed in slides) Subscribes to React context.

### E. List Programming in React
*   JSX elements are first-class objects.
*   Use array methods like `map()` to render lists of components/elements.
*   **Keys:** Special string attribute needed when creating lists of elements.
    *   Help React identify which items have changed, are added, or are removed.
    *   Should be unique among siblings.
    *   Often use item IDs as keys: `<li key={item.id}>{item.text}</li>`.
*   Example: To-Do List
    *   `TodoList` component receives `todos` array and `filter` prop.
    *   Filters todos, then maps over `filteredTodos` to render `<li>` elements.

### F. Demo Web Page Walkthrough
*   **App Component (`App.jsx` or `App.tsx`):**
    *   Top-level structure.
    *   Manages `searchTerm` state using `useState`.
    *   `handleSearch` function updates `searchTerm`.
    *   Filters `products` based on `searchTerm` to get `searchedProducts`.
    *   Renders `Search` and `ProductList` components.
*   **Search Component:**
    *   Defines the search input box.
    *   Receives `searchTerm` (value) and `onInputChange` (handler) as props.
*   **ProductList Component:**
    *   Receives `searchedProducts` array as prop.
    *   Maps over `searchedProducts` to render `ProductCard` components for each product.
*   **ProductCard Component:**
    *   Receives product data (e.g., `item`) as prop.
    *   Defines the UI for displaying a single product (image, name, price, etc.).

## 14. Next.js
*(Corresponds to original topic 19: Next.js I - Slides 717-742, original topic 20: Next.js II - Slides 743-793, original topic 24: Next.js III - Slides 922-956)*

### A. Introduction to Next.js
*   React framework for building full-stack web applications.
*   Extends React with features for server-side rendering, routing, API routes, etc.
*   Improves: Initial page load performance, SEO, user experience on slower devices.
*   **Website Repo:** `gitlab.com/comp315/website` (course demo).

### B. Rendering Strategies
*   **Client-Side Rendering (CSR):**
    *   Browser downloads minimal HTML + JS bundle. JS executes to render page (React's default).
    *   Disadvantage: Slow initial load (download + execution).
    *   Advantage: Fast re-renders for small UI updates.
    *   React's `index.html` is minimal, with a root div for mounting.
*   **Server-Side Rendering (SSR):**
    *   Server generates HTML for the page per request, sends to browser.
    *   Browser receives HTML, parses, constructs DOM quickly.
    *   Advantage: Fast initial page load, good for SEO.
    *   Disadvantage: Can be slower for small re-renders (entire page re-rendered on server).
*   **Rendering in Next.js:**
    *   Default: Server-side rendering (or Static Site Generation for pages without dynamic data).
    *   Generates HTML per page in advance (SSR/SSG).
    *   Small amount of JS sent for interactivity (**hydration**).
    *   **Hydration:** Process where client-side JS makes the server-rendered HTML interactive.
*   **Specifying SSR vs. CSR in Next.js (App Router):**
    *   Default is Server Components (SSR/SSG).
    *   To opt into CSR for a component: Add `"use client";` directive at the top of the component file.
*   **React Recommends Next.js:** React is now often used within a framework like Next.js.

### C. Starting a Next.js Project
*   `npx create-next-app@latest`.
*   Interactive setup: Prompts for project name, TypeScript, ESLint, Tailwind CSS, `src/` directory, App Router.
*   **App Router:** Recommended; file-system based routing within the `app` directory. (vs. older Pages Router).
*   **Docker Support:** Add `Dockerfile` and `.dockerignore` (e.g., from Vercel examples).
*   Run locally: `npm run dev`.
*   Build Docker image: `docker build -t my-next-app .`.
*   Run Docker container: `docker run -p 3000:3000 my-next-app`.
*   **Directory Structure (App Router):**
    *   `app/`: Core directory for App Router.
        *   `layout.tsx` (or `.js`): Root layout, shared UI.
        *   `page.tsx` (or `.js`): UI for a route segment, makes route publicly accessible.
        *   Folders define route segments.
    *   `public/`: Static assets.
    *   `components/` (often in `src/`): Reusable UI components.
    *   `next.config.js`: Next.js configuration.

### D. App Router
*   File-system based routing within the `app` directory.
*   **Terminology:**
    *   **URL Segment:** Part of URL path delimited by slashes.
    *   **URL Path:** Part of URL after domain, composed of segments.
*   **Route Segments:** Each folder in `app/` represents a route segment.
*   **Nested Routes:** Created by nesting folders (e.g., `app/dashboard/settings/page.tsx` maps to `/dashboard/settings`).
*   **Dynamic Routes:**
    *   For routes with dynamic data (e.g., blog post slugs, product IDs).
    *   Created by wrapping folder name in square brackets: `[folderName]` (e.g., `app/blog/[slug]/page.tsx`).
    *   Dynamic segment value passed as `params` prop to page/layout.
    *   Example: `app/blog/[slug]/page.js` -> `/blog/a` (params: `{ slug: 'a' }`).
*   **File Conventions (Special Files in `app/`):**
    *   `layout.js` / `.tsx`: Shared UI for a segment and its children.
    *   `page.js` / `.tsx`: Unique UI for a route, makes it accessible.
    *   `loading.js` / `.tsx`: Loading UI (React Suspense boundary).
    *   `error.js` / `.tsx`: Error UI (React Error Boundary).
    *   `not-found.js` / `.tsx`: UI for 404 errors.
    *   `route.js` / `.ts`: Server-side API endpoints (Route Handlers).
*   **Component Hierarchy:** Order in which special files are rendered (layout -> template -> error -> loading -> not-found -> page).
*   **Colocation:** Store related files (components, styles, tests) within route segment folders. Only `page.js` and `route.js` are publicly addressable.
*   **Advanced Routing Patterns:** Parallel Routes, Intercepting Routes.

### E. Route Handlers
*   Create custom API endpoints (server-side) within `app` directory using `route.js` or `route.ts`.
*   Use Web Request and Response APIs.
*   Support HTTP methods (GET, POST, PUT, PATCH, DELETE, HEAD, OPTIONS).
*   Example: `app/api/items/route.ts` can define `export async function GET(request: Request) { ... }`.
*   `export const dynamic = 'force-dynamic';` to ensure dynamic rendering per request.
*   **Caching:**
    *   `GET` requests with `Response` object are cached by default.
    *   Opt out of caching:
        *   Use `Request` object with `GET`.
        *   Use other HTTP methods (POST, PUT, etc.).
        *   Use dynamic functions (cookies, headers).
        *   Segment Config Option `export const dynamic = 'force-dynamic';`.

### F. Data Fetching
*   **Server Components (Default in App Router):**
    *   Can fetch data directly using `async/await` with `fetch`.
    *   Next.js extends `fetch` API for caching and revalidation.
    *   Example: `async function getData() { const res = await fetch(...); return res.json(); } async function Page() { const data = await getData(); ... }`.
*   **Client Components (`"use client";`):**
    *   Fetch data via Route Handlers (API endpoints) or third-party libraries (e.g., SWR, React Query).
    *   Route Handlers execute on server, return data to client (good for hiding API keys).
*   **Caching with `fetch` on Server:**
    *   Next.js automatically caches `fetch` results in the Data Cache.
    *   Data fetched at build time (SSG) or request time (SSR) can be cached and reused.
    *   Exceptions (not cached): Inside Server Actions, POST requests in Route Handlers.
*   **Data Cache:** Persistent HTTP cache provided by Next.js.
*   **Revalidating Data:** Purging cache and re-fetching.
    *   **Time-based Revalidation:**
        *   `fetch(url, { next: { revalidate: 3600 } })` (revalidate every hour).
        *   Segment Config: `export const revalidate = 3600;` in `layout.js` or `page.js`.
    *   **On-demand Revalidation:**
        *   `revalidatePath(path)`: Revalidate by path.
        *   `revalidateTag(tag)`: Revalidate by cache tag.
            *   Tag fetch requests: `fetch(url, { next: { tags: ['collection'] } })`.
            *   Call `revalidateTag('collection')` in a Server Action or Route Handler.
*   **Opting out of `fetch` Caching:**
    *   `fetch(url, { cache: 'no-store' })`.
    *   `fetch(url, { next: { revalidate: 0 } })`.
    *   If fetch uses dynamic functions like `headers()` or `cookies()`.
    *   If Route Handler uses POST method.
    *   Segment config `export const dynamic = 'force-dynamic';`.

### G. Server Actions & Forms
*   **HTML Forms Recap:** `<form action="/submit-url" method="post">`, `<input>`, `<label>`, `<textarea>`, `<button type="submit">`.
*   **Server Actions:** Asynchronous functions executed on the server.
    *   Handle form submissions and data mutations.
    *   Defined with `"use server";` directive.
        *   Inline: At top of `async function create() { "use server"; ... }`.
        *   Module-level: At top of a file (`actions.ts`), all exports become server actions.
*   **Usage:**
    *   **Server Components:** Can define inline server actions or import module-level ones.
    *   **Client Components:** Can only import module-level server actions or receive them as props.
*   **Forms and Progressive Enhancement:**
    *   React extends `<form>` with `action` prop to invoke server actions.
    *   `FormData` object automatically passed to action.
    *   Server Components: Forms work even if JS is disabled (progressive enhancement).
    *   Client Components: Forms queue if JS not loaded; no full refresh after hydration.
*   **`useActionState` Hook:**
    *   Updates state based on form action result.
    *   `const [state, formAction, isPending] = useActionState(actionFunction, initialState);`.
    *   `formAction` is passed to `<form action={formAction}>`.
    *   `state` holds the return value of `actionFunction` or `initialState`.
    *   Supports progressive enhancement with optional third argument (permalink for redirection if JS disabled).
*   **Example (Form with Server Action):**
    *   Form component (`<form action={createInvoice}> ... </form>`).
    *   Server Action (`createInvoice` function with `"use server";`):
        ```javascript
        // in app/lib/actions.ts (example)
        'use server';
        export async function createInvoice(formData: FormData) {
          const rawFormData = {
            customerId: formData.get('customerId'),
            amount: formData.get('amount'),
            status: formData.get('status'),
          };
          // ... validate and save to database ...
          console.log(rawFormData);
        }
        ```
    *   Server terminal shows logged data on submission.

### H. Deploying Next.js Applications
*   Options:
    *   Vercel (managed Next.js hosting, by creators of Next.js).
    *   Self-hosting: Node.js server, Docker image, static HTML files.
*   `npm run build`: Generates optimized production build.
    *   Creates HTML, CSS, JS files.
    *   Compiles JS, creates browser bundles.
*   Self-hosting with Docker and Kubernetes is a common approach covered in the course.
