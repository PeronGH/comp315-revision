# COMP315 Revision Notes

## Data Centres

*   **A Data Centre Tour**
    *   Physical appearance:
        *   External View (e.g., AWS Data Centre).
        *   Internal View (e.g., Google Data Centre with rows of server racks).
    *   Key Hardware Components (Visuals):
        *   **Server Rack**: Structure for housing multiple servers and networking equipment.
        *   **Server**: Individual computer unit performing computations.
        *   **Network Switch**: Device connecting servers and other network components.
    *   Cooling Systems:
        *   **Server Cooling**: Airflow mechanisms within individual servers.
        *   **Rack Cooling**: Methods for cooling entire racks, often involving airflow management like raised floors for cold air intake.
        *   **Other Cooling Approaches**: Locating in cool climates, underwater data centres (e.g., Microsoft's Project Natick).
    *   Other Data Centre Tours (Links mentioned for further interest).
*   **Data Centre Hardware Components**
    *   **Commodity Hardware**:
        *   Definition: Standard, relatively inexpensive, and readily available hardware components ("off-the-shelf").
        *   Characteristics: Similar to desktop PC hardware but typically with higher specifications for reliability and performance.
        *   Rationale: Cost-effectiveness, ease of replacement and scalability.
    *   **Compute Resources**:
        *   Server Components: CPUs, RAM, hard disks, network cards. Servers in data centres typically operate without dedicated monitors, keyboards, or mice ("headless").
        *   Mounting: Typically rack-mounted.
        *   **Top-of-Rack (ToR) Switch**:
            *   Connects all servers within the same rack.
            *   Connects the rack to the broader data centre network.
        *   Storage: Hard drives can be located directly on servers and/or accessed via the network.
    *   **Local Networks vs. The Internet**:
        *   **Local Area Networks (LANs)**:
            *   Scope: Limited geographic area (e.g., single building, campus).
            *   Ownership: Typically owned, managed, and maintained by a single organization.
            *   Examples: Office networks, home networks.
        *   **The Internet**:
            *   Scope: Global network connecting millions of private, public, academic, business, and government networks.
            *   Ownership: No single entity owns the Internet; it's a network of networks.
    *   **Network Interface Cards (NICs)**:
        *   Function: Allow hardware components (servers, etc.) to connect to a network.
        *   Aliases: Network interfaces, network adaptors, network cards (Visual provided).
    *   **MAC Addresses**:
        *   Definition: Unique Media Access Control address assigned to each NIC.
        *   Assignment: Set by the manufacturer ("burned-in address," though now usually in firmware).
        *   Uniqueness: Identifies the NIC globally.
        *   Format: Six pairs of hexadecimal digits (e.g., `00:1A:2B:3C:4D:5E`).
            *   First three pairs: **Organizationally Unique Identifier (OUI)** (identifies the manufacturer).
            *   Last three pairs: **NIC-Specific Identifier** (device-specific part). (Diagram provided).
    *   **Network Switches**:
        *   Function: Connect devices *within* a single computer network (e.g., within a LAN or a data centre rack). (Visual provided).
    *   **Routers**:
        *   Function: Connect *multiple different* networks together and facilitate data transfer *between* them. (Visual provided).
    *   **Firewalls**:
        *   Function: Network security devices that monitor and filter incoming and outgoing network traffic based on a set of security rules.
        *   Placement: Typically at the boundary of a network.

## Server Software

*   **Operating Systems (OS) for Cloud Servers**
    *   Core Functions: Manage hardware/software resources (CPU, memory, I/O, files), provide user interface (GUI/CLI).
    *   Dominant Cloud Server OS: **Linux**.
    *   **Linux Overview**:
        *   Free and open-source family of operating systems.
        *   Built on the Linux kernel.
        *   Created by Linus Torvalds in 1991.
        *   Distributions: RHEL (Red Hat Enterprise Linux - typical for cloud servers), Ubuntu, Fedora, Debian, CentOS.
    *   **The Linux Kernel**:
        *   Heart of Linux OS.
        *   Manages hardware resources, provides essential services to software.
        *   Handles requests from applications to access hardware.
        *   Functions: Process management, memory management, device drivers.
    *   **Kernel Space vs. User Space**:
        *   **Kernel Space**: Privileged area where the kernel operates with complete hardware access; protected memory.
        *   **User Space**: Area where user applications run with limited hardware access; must communicate with kernel for resource access.
        *   Diagram: Applications (User Space) -> Linux Kernel -> (Device Modules -> Devices), (CPU), (Filesystem Module -> Memory) (Kernel Space).
    *   **The Root User**:
        *   Special user account with highest system privileges (operates in user space but can initiate kernel-level actions).
        *   Capabilities: Modify system settings, manage user accounts.
        *   Risks: Potential for significant system damage if used improperly. Best practice: use only when necessary.
*   **Virtualisation**
    *   Definition: Creating virtual versions of physical components (servers, storage devices, networks, NICs).
    *   **Virtual Machines (VMs)**: Software emulations of an entire physical server.
    *   **Hypervisor**: Software layer enabling VM creation and management.
        *   **Type 1 (Bare-Metal) Hypervisors**:
            *   Run directly on host hardware.
            *   Also known as bare-metal hypervisors.
            *   High performance and efficiency (close to bare metal).
            *   Examples: VMware ESXi, Microsoft Hyper-V.
            *   Tech Stack: Application -> VM -> Hypervisor -> Hardware (Diagram provided).
        *   **Type 2 (Hosted) Hypervisors**:
            *   Run on a host operating system.
            *   Also known as hosted hypervisors.
            *   Easier to set up and use.
            *   Examples: VMware Workstation, Oracle VirtualBox.
    *   **Benefits of Virtualisation**:
        *   Efficiency: Maximizes resource utilization.
        *   Cost Savings: Reduces need for physical hardware.
        *   Flexibility: Eases deployment and management of IT environments.
        *   Isolation: Provides secure and isolated environments (though sandboxing like SELinux offers more robust application isolation).

## HTML and CSS

*   **Foundation of Front-End Web Development**:
    *   **HTML (HyperText Markup Language)**: Defines the *structure* of web pages. Used with CSS for layout.
    *   **CSS (Cascading Style Sheets)**: Describes the *look and formatting* (style and layout) of HTML documents. Provides visual aspects HTML is not designed for.
    *   **JavaScript**: Object-oriented programming language for *interactivity* and dynamic behavior in web pages.
*   **HTML Details**:
    *   Combines **Hypertext** (text that links to other text/documents) and **Markup** (system for annotating text).
    *   Simple Document Example: `<html><head><title>My Page</title></head><body><h1>Welcome</h1><p>This is a paragraph.</p></body></html>`. (Visual of rendered page provided).
    *   **Tags and Elements**: Annotations like `<body>` and `</body>` define elements. Elements can be nested.
*   **The DOM (Document Object Model)**:
    *   Programming interface for web documents.
    *   Tree-like representation of the HTML structure.
    *   Initially populated from page's HTML; HTML tags become nodes.
    *   Allows JavaScript to dynamically manipulate content, structure, and style in response to user actions (e.g., clicking buttons).
    *   DOM Example Diagram: `document` -> `html` -> (`head` -> `title` -> "text: My Page", `body` -> (`h1` -> "text: Welcome"), (`p` -> "text: This is a paragraph.")).
*   **CSS Details**:
    *   Modifies style and layout (font, color, size, spacing, columns, animations, decorative features).
    *   Example CSS Script: `body { font-family: Arial, sans-serif; background-color: lightblue; } h1, p { color: darkred; /* Sets text color to dark red */ }`.
    *   Adding CSS to HTML: `<link rel="stylesheet" type="text/css" href="webpage1.css">` within the `<head>`.
    *   DOM Representation with CSS Styles: Diagram shows styles applied to DOM nodes.
    *   Web Page Example with CSS (Visual provided).
*   **HTML Element Attributes**:
    *   Provide additional information about elements.
    *   `class`: Specifies one or more class names (for CSS styling or JS selection).
    *   `id`: Specifies a unique ID for an element (for CSS styling or JS selection via DOM).
    *   `style`: Specifies inline CSS style for an element.
*   **Tailwind CSS**:
    *   Tool for conveniently adding CSS styling.
    *   Adds classes to individual HTML elements, removing need for separate CSS scripts for many styles.
    *   Build completely custom designs within HTML.
    *   Example: `<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Shop Online</button>`.
    *   Online Store Example (HTML code and rendered page visual provided).
    *   Explanation of Tailwind Classes: `bg-blue-900`, `text-center`, `text-white`, `bg-blue-700`, `p-4`, `my-4`, `text-3xl`, `font-bold`, `underline`, `mt-4`.
*   **Enhancing Web Pages with JavaScript**:
    *   Adds interactivity and dynamic behavior.
    *   Respond to user events (clicks, key presses).
    *   Manipulate and update the DOM.
    *   Make network requests without reloading pages.
    *   JavaScript Example (for button clicks): `window.onload`, `document.querySelector()`, `addEventListener()`. Modifications to HTML for unique classes. Alert dialog visual.

## Javascript

*   **Running JavaScript**:
    *   Browser Console (e.g., Chrome DevTools). Warning about pasting code.
    *   Command Line with Node.js (JavaScript runtime built on Chrome's V8 engine). Install from `nodejs.org`. `node` for interactive shell, `.exit` to quit.
    *   Console Example: `let x = 10; x + 5; let y = 'Hello'; y.toUpperCase();`.
*   **JavaScript Basics**:
    *   **Primitive Types**: `Undefined`, `Null`, `Boolean` (true/false), `Number` (integers and floats), `String`, `Symbol` (ES6, unique identifiers for objects), `BigInt` (ES2020, arbitrary-length integers). Everything else (e.g., functions) is an object.
    *   **Undefined vs. Null**:
        *   `Undefined`: Variable declared but not assigned; value returned by functions not explicitly returning anything; accessing non-existent object property.
        *   `Null`: Intentional absence of any object value ('no-value' or 'no-object' state); must be explicitly assigned.
    *   **Expressions vs. Statements**:
        *   Expressions: Any valid unit of code that resolves to a value (e.g., `2 + 2`, `'hello' + 'world'`, `console.log('Hello')`).
        *   Statements: Perform an action (e.g., `var x = 10;`, `if (x > 10) {...}`, `for (...) {...}`). Control program flow. Semicolons separate statements.
    *   **Variable Declaration (`let`, `const`, `var`)**:
        *   `let`: Block-scoped, can be updated but not re-declared in the same scope. Preferred for variable declaration due to block scoping.
        *   `const`: Block-scoped, cannot be re-declared or updated (must be initialized). Used when value should not change.
        *   `var`: Function-scoped (older, generally avoid due to hoisting and complicated behavior).
    *   **Scope**: Function scope (for `var` - example provided) vs. Block scope (for `let`, `const` - example provided).
    *   **Truthiness and Falsiness**:
        *   How values behave in boolean contexts (e.g., `if` statements).
        *   Truthy values: Most values unless defined as falsy (e.g., `{}`, `[]`, `42`, `"false"`, `new Date()`, `-42`, `3.14`, `Infinity`, all objects).
        *   Falsy values: `false`, `0`, `-0`, `0n` (BigInt zero), `""` (empty string), `null`, `undefined`, `NaN`.
        *   Truthy/Falsy Example in JS (code provided).
        *   Gotchas: Empty arrays/objects are truthy; string `"0"` is truthy; `NaN` is falsy.
    *   **Equality Operators**:
        *   `==` (Double Equals): Loose equality, performs type coercion if types differ.
        *   `===` (Triple Equals): Strict equality, no type coercion (preferred for predictability).
        *   Console examples: `0 == false` (true), `0 === false` (false), `null == undefined` (true), `"5" == 5` (true).
    *   **Template Literals**: Backticks (`` ` ``) for strings with embedded expressions: `` `Hello, ${name}!` ``.
*   **Compound Data Types**:
    *   **Arrays**: Ordered collections of elements, 0-indexed. `let numbers = [1, 2, 3, 4, 5];`. Similar to Python lists.
        *   Methods: `push()`, `pop()`, `shift()`, `unshift()`, `slice()`, `splice()`, `concat()`.
    *   **Objects**: Collections of key-value properties. `let student = { name: "John", age: 20, grade: "A" };`.
        *   Accessing/Modifying/Adding properties: `student.name`, `student.age = 21;`, `student.major = "CS";`.
    *   **Methods and `this` keyword**:
        *   Methods are functions that are properties of objects.
        *   `this` refers to the object the method is called on. Its value depends on how the function is called (in a method, alone, in a regular function, in strict mode). Example with `person` object.
    *   **Strict Mode (`"use strict";`)**: Placed at beginning of script/function. Eliminates some silent errors. `this` is `undefined` in functions not called as methods/constructors. Example provided.
    *   **Object Literals vs. Object Constructors**: `let obj = {key: value};` vs `let obj = new Object(); obj.key = value;`. Literals are generally preferred.
    *   Standard Object Methods: `Object.keys(obj)`, `Object.entries(obj)`, `Object.assign(target, ...sources)`.
    *   **Functions are Objects**: Can have properties and methods. `myFunction instanceof Object` is true.
    *   **Object Destructuring**: `const { name, age, major } = student;`.
    *   **Spread Operator (`...`)**: Expands iterables into arguments/elements or object properties into new objects. `[...arr1, 4, 5]`, `{ ...obj1, ...obj2 }`.
    *   **Prototype Chains & Inheritance**:
        *   Objects have a hidden `[[Prototype]]` property (either `null` or references another object - "a prototype").
        *   Properties/methods not found on an object are looked up on its prototype (prototype inheritance).
        *   Methods usually come from prototype, properties stored in object itself.
        *   Example: `animal` object, `rabbit` object with `__proto__: animal`.
        *   `Object.create(proto)` can create an object with a specified prototype.
*   **Conditionals and Loops**:
    *   `if/else if/else`, ternary operator (`condition ? valIfTrue : valIfFalse`).
    *   `switch` statement.
    *   `for` loop (`for (let i = 0; i < 5; i++)`).
    *   `for...of` loop (ES6, for iterable objects like arrays, strings).
    *   `for...in` loop (for an object's enumerable properties/keys).
    *   `while` and `do...while` loops.
*   **Functions**:
    *   Function declarations (`function greet1(name) {...}`), function expressions (`const greet2 = function(name) {...}`), arrow functions (`const greet3 = (name) => {...}`).
    *   Rest Parameters: `function sum(...numbers) { ... }` (collects arguments into an array).
*   **Classes (ES6 syntax)**:
    *   Templates for creating objects; syntactic sugar over prototypal inheritance.
    *   `constructor`, methods. Example `Car` class with `constructor(brand)` and `present()` method.
    *   Creating an object: `let myCar = new Car("Ford");`.
    *   Inheritance: `class Model extends Car { constructor(brand, mod) { super(brand); this.model = mod; } }`.
*   **JSON (JavaScript Object Notation)**:
    *   Text format for representing JS objects.
    *   Syntax: Objects `{}`, arrays `[]`. Keys and strings in double quotes. Numbers, booleans (`true`/`false`), `null`.
    *   Primitives in JSON example.
    *   Arrays in JSON example.
    *   Serialization: `JSON.stringify(jsObject)` (JS object to JSON string).
    *   Deserialization: `JSON.parse(jsonString)` (JSON string to JS object).
*   **YAML (YAML Ain't Markup Language)**:
    *   Human-readable data serialization format, more popular than JSON for config.
    *   Syntax: Indentation-based. Key-value pairs.
    *   Optional start/end markers: `---` and `...`.
    *   Primitives: Strings (can be unquoted), numbers, booleans (truthy/falsy values like `true`, `yes`, `on`, `false`, `no`, `off`), `null` (or `~` or empty).
    *   Lists: `- item1\n- item2`.
    *   Dictionaries (Objects): `key:\n  subkey: value`.

## Networking

*   **Introduction**: How computers connect to provide services (web hosting, email, SSH). Illustrative example of visiting a website.
*   **Protocols and Protocol Stacks**:
    *   **Protocols**: Sets of rules defining how machines interact and exchange information.
    *   **Protocol Stacks**: Layered organization. Lower layers provide basic services (bit transmission), higher layers provide complex services (reliable data delivery, security).
*   **Main Protocol Stacks**:
    *   **TCP/IP**: Most widely used, practical model for the internet. Stands for Transmission Control Protocol/Internet Protocol.
    *   **OSI Model (Open Systems Interconnection)**: Conceptual 7-layer framework for understanding network interactions.
*   **OSI Model Layers (and corresponding TCP/IP layers)**:
    *   **Layer 7: Application**: High-level protocols for resource sharing, remote file access (e.g., HTTP). (TCP/IP: Application)
    *   **Layer 6: Presentation**: Translation, character encoding, compression, encryption/decryption. (TCP/IP: Application)
    *   **Layer 5: Session**: Managing communication sessions (establishment, maintenance, termination). (TCP/IP: Application)
    *   **Layer 4: Transport**: Reliable end-to-end data segment transmission (e.g., TCP, UDP). (TCP/IP: Transport)
    *   **Layer 3: Network**: Structuring and managing multi-node network, packet routing (e.g., IP). (TCP/IP: Internet)
    *   **Layer 2: Data Link**: Transmission of data frames between two nodes on same physical layer (e.g., Ethernet, MAC addresses). (TCP/IP: Physical/Link)
    *   **Layer 1: Physical**: Transmission/reception of raw bit streams over a physical medium. (TCP/IP: Physical/Link)
    *   (Diagram comparing OSI and TCP/IP stack layers provided).
*   **Detailed OSI Stack and its Protocols**:
    *   **3 Types of Address**:
        *   **Domain Name**: Human-readable (e.g., `google.com`), resolved to IP.
        *   **IP Address**: Numerical, Layer 3 (e.g., `192.168.1.10`).
        *   **MAC Address**: Unique hardware identifier, Layer 2 (e.g., `00:1A:2B:3C:4D:5E`).
    *   **Layer 1: The Physical Layer**: Deals with bits (0s and 1s), transmission media (copper, fiber, radio), electrical/optical signals, voltages, timing, connectors.
    *   **Layer 2: The Data Link Layer (Ethernet)**: Communication between physically close devices.
        *   Uses **Ethernet protocols** to organize bits into **frames**.
        *   Communication mediated by **switches** (Ethernet switches / L2 switches).
        *   **Ethernet Frames**: Structure: Dest MAC, Source MAC, Type, Data, CRC (Cyclic Redundancy Check for error detection).
        *   MAC Address Refresher (OUI, NIC-Specific).
    *   **Layer 3: The Network Layer**: Logical addressing and routing of data **packets**.
        *   **IP (Internet Protocol)**: Decides best path. Connectionless (packets treated independently).
        *   Key IP Functions: Addressing, Routing, Fragmentation & Reassembly, Packet Forwarding.
        *   **IP Versions**: IPv4 (32-bit, e.g., `192.168.0.1`), IPv6 (128-bit, e.g., `2001:0DB8:ABCD:...`). Formats shown.
        *   **Routers** operate at this layer. Can lose packets.
    *   **Layer 4: The Transport Layer**: End-to-end communication, quality, and reliability.
        *   **TCP (Transmission Control Protocol)**: Reliable, ordered, error-checked, connection-oriented delivery of a stream of data.
        *   **UDP (User Datagram Protocol)**: Prioritizes speed over reliability; connectionless. Used for time-sensitive apps (e.g., live video).
        *   **Port Numbers**: Used with TCP/UDP to specify application/service on a host (e.g., `:80` for HTTP). IPv4 Address with Port Number format shown.
        *   **SSL (Secure Sockets Layer) / TLS (Transport Layer Security)**: Secure communication via encryption. TLS is successor to SSL.
            *   Properties: Confidentiality (symmetric-key encryption), Encryption Negotiation, Authentication (public-key crypto, server certs), Integrity (message auth code).
            *   **TLS Handshake**: Client initiates, server responds with certificate, client verifies, session keys generated.
            *   **Certificate Authorities (CAs)**: Issue digital certificates (e.g., Let's Encrypt for HTTPS).
    *   **Layer 5: The Session Layer**: Manages establishment, maintenance, termination of communication sessions. Dialog control.
    *   **Layer 6: The Presentation Layer**: Data translation, formatting, encryption/decryption, compression, format conversion.
    *   **Layer 7: The Application Layer**: Services directly to end-users/applications.
        *   Protocols: HTTP, SMTP, FTP, DNS.
        *   **HTTP and HTTPS**: HTTP (Hypertext Transfer Protocol) requires reliable transport (TCP usually). HTTPS is HTTP over TLS/SSL.
        *   **HTTP Methods (Verbs)**: `GET` (retrieve), `POST` (submit entity, side effects), `PUT` (replace resource), `DELETE` (remove resource), `PATCH` (partial modification).

## Ansible

*   **Configuration as Code (CaC)**: Managing configurations using code. Ansible is a popular tool for this.
*   **Ansible Overview**:
    *   Tool for configuration management, application deployment, task automation.
    *   **Agentless Architecture**: Communicates with managed nodes over SSH. Temporary modules are pushed, executed, and then removed. No persistent agents.
    *   **SSH (Secure Shell)**: Protocol for secure remote login and command execution. `ssh username@remote_host`. PuTTY for Windows.
    *   Agentless Architecture Diagram: Ansible Controller -> SSH -> Managed Nodes (No agent).
*   **Inventory**:
    *   Defines hosts (servers) and groups of hosts that Ansible manages.
    *   Formats: YAML (e.g., `leafs: hosts: { leaf01: { ansible_host: 10.16.10.11 } }`) or INI (e.g., `[leafs]\nleaf01 ansible_host=10.16.10.11`).
    *   Static (defined in files) or Dynamic (from cloud APIs etc.).
    *   Variables in inventory: `ansible_host` (IP/hostname), `ansible_connection: local` (for localhost).
    *   `ansible` command-line tool for ad-hoc commands (e.g., `ansible local -i hosts.ini -m ping`). Output shows facts.
*   **Playbooks**:
    *   YAML files defining a desired state and a set of tasks to achieve it.
    *   **Idempotency**: A key feature. Operations only make changes if the current state differs from the desired state. Safe to re-run.
    *   Structure:
        *   **Plays**: Top-level unit in a playbook. Maps hosts/groups to tasks. `hosts: all`, `become: yes` (for privilege escalation, like `sudo`).
        *   **Tasks**: Individual actions performed by Ansible modules. Each task has a `name`.
        *   **Modules**: Reusable units of code that perform specific operations (e.g., `ansible.builtin.yum` for RHEL/Rocky, `ansible.builtin.service`, `ansible.builtin.file`, `ping`, `debug`, `ansible.posix.selinux`, `ansible.builtin.reboot`, `ansible.builtin.lineinfile`, `ansible.builtin.copy`, `ansible.builtin.shell`, `ansible.builtin.dnf`).
        *   **Conditionals (`when`)**: Execute tasks based on conditions. `when: ansible_selinux.status == "enabled"`. Variables used directly.
        *   **Variables (`register`)**: Store the output of a task in a variable. `register: command_output`. Access with `command_output.rc`, etc.
        *   **Variable Interpolation**: `{{ variable_name }}`. Used in `debug: msg: "Output is {{ result }}"`.
        *   **Loops (`loop`)**: Iterate over a list of items. `loop: "{{ range(1, 4) | list }}"`, `loop_control: { label: "Ping number {{ item }}" }`.
        *   **Handlers**: Tasks triggered by `notify` directives in other tasks, typically used for service restarts after configuration changes.
*   **Ansible Variables**:
    *   Defined in playbooks (`vars:` section), inventory files.
    *   **Variable Directories**: `group_vars/` (files named after groups) and `host_vars/` (files named after hosts) for organizing variables. Example with `group_vars/lamp` file.
    *   **Facts**: System information automatically gathered by Ansible about managed nodes (e.g., IP address, OS, hostname). Accessed via `ansible_facts` or `ansible_default_ipv4.address`.
        *   `ansible all -m setup` to view facts.
        *   Playbook to print all facts (`debug: var: ansible_facts`).
        *   Playbook to print specific fact (`debug: msg: "IP: {{ ansible_facts.default_ipv4.address }}"`).
*   **Ansible Vault**:
    *   Encrypts sensitive data (passwords, API keys, private keys, configuration files) in variable files.
    *   Data remains encrypted at rest, decrypted at runtime.
    *   Commands: `ansible-vault create secret.yml`, `ansible-vault edit`, etc. Prompts for vault password.
    *   Using vaulted files in playbooks: `vars_files: - secret.yml`.
    *   Running playbooks with vaulted files: `ansible-playbook --ask-vault-pass ...`.
    *   Password Hashing: `{{ 'mypassword' | password_hash('sha512') }}` filter for user module.
*   **Everything as Code (EaC)**:
    *   Concept of managing every part of a software system (infrastructure, configuration, build, deployment, monitoring) as code.
    *   Benefits: Version control, consistency, repeatability, automated testing.
    *   **Configuration as Code (CaC)**: Ansible's primary domain. Managing system configurations via code.
    *   **Infrastructure as Code (IaC)**: Provisioning and managing infrastructure (VMs, networks) using code (e.g., Terraform; Ansible can also be used for IaC).
    *   **Declarative vs. Imperative Approaches**:
        *   Declarative: Define desired state (Ansible generally).
        *   Imperative: Specify commands to achieve state.
    *   Benefits of IaC: Cost reduction, speed of deployments, error reduction, consistency, eliminates configuration drift.
*   **Anything as a Service (XaaS)**:
    *   Cloud provider service models.
    *   **IaaS (Infrastructure as a Service)**: Basic building blocks (VMs, storage, networking). Highest flexibility and control.
    *   **PaaS (Platform as a Service)**: Platform and environment for developers (e.g., Kubernetes, Heroku). Manages underlying infra.
    *   **SaaS (Software as a Service)**: Completed product run and managed by provider (e.g., Gmail, Office 365).
    *   Diagram illustrating IaaS, PaaS, SaaS layers and responsibilities.

## Hosting

*   **Introduction**: How websites are hosted using web servers.
*   **Web Servers**: Software that hosts and serves web content (HTML, CSS, JS) to clients over the internet (e.g., Apache, NGINX).
*   **Proxies**:
    *   **Forward Proxy**: Acts as an intermediary for clients accessing the internet.
        *   Use cases: Caching, anonymizing client requests, access control/content filtering.
        *   Diagram: Client(s) -> LAN -> Forward Proxy -> Internet -> Web Server(s).
        *   Case Study: University Intranet (managing bandwidth, secure access, monitoring).
    *   **Reverse Proxy**: Sits between the internet and web servers.
        *   Use cases: Load balancing, enhancing security (hiding backend IPs), SSL termination, caching static content.
        *   Diagram: Client(s) -> Internet -> Reverse Proxy -> Web Server LAN -> Web Server(s).
        *   Case Study: E-Commerce Website (managing high traffic, protecting backend, availability, caching).
*   **Apache HTTP Server**:
    *   Popular open-source web server.
    *   Workflow: Handles requests -> Processes requests (serves static files) -> Serves content.
    *   **Setting up an HTTP Server with Docker**:
        *   HTML Code example (recap from previous lectures).
        *   Dockerfile: `FROM httpd:latest`, `COPY index.html /usr/local/apache2/htdocs/`, `EXPOSE 80`.
        *   Building: `docker build -t apache-image .`.
        *   Running: `docker run --name apache-container -p 8081:80 apache-image`. Port mapping `host_port:container_port`.
        *   Accessing: `http://localhost:8081`.
        *   Accessing Apache Config: `docker exec -it apache-container /bin/bash`, config file at `/usr/local/apache2/conf/httpd.conf`. `docker cp` to copy out.
        *   `DocumentRoot` directive in `httpd.conf`.
    *   **Adding HTTPS to Apache**:
        *   Requires TLS, certificates (CA-signed or self-signed).
        *   Generating Self-Signed Certificate with `openssl`: `openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out selfsigned.crt -subj "/C=UK/ST=Merseyside/L=Liverpool/O=MyOrg/CN=www.example.com"`.
        *   Apache SSL Configuration (`httpd-ssl.conf`): `Listen 443`, `<VirtualHost *:443>`, `SSLEngine on`, `SSLCertificateFile`, `SSLCertificateKeyFile`, `DocumentRoot`.
        *   Updating Dockerfile for HTTPS: `COPY` certs/key/ssl-config, `RUN sed` to uncomment SSL modules (`ssl_module`, `socache_shmcb_module`) in `httpd.conf`, `RUN echo 'Include conf/extra/httpd-ssl.conf' >> .../httpd.conf`, `EXPOSE 80 443`.
        *   The `sed` command: Stream editor, `-i` for in-place, `s/old/new/` for substitution.
        *   Building/Running HTTPS Docker: Map port 443 (e.g., `-p 8082:443`).
        *   Certificate Warning in browser for self-signed certs.
*   **NGINX as a Reverse Proxy**:
    *   Requires Docker Networking: `docker network create web-net`.
    *   NGINX Configuration (`nginx.conf`):
        *   `upstream apache-server { server apache-container:80; }`
        *   `server { listen 80; location / { proxy_pass http://apache-server; } }`
    *   Dockerfile for NGINX: `FROM nginx:latest`, `RUN rm /etc/nginx/conf.d/default.conf`, `COPY nginx.conf /etc/nginx/conf.d/`, `EXPOSE 80`.
    *   Building/Running NGINX Container: Connect to `web-net`, map host port (e.g., `-p 8083:80`).

## Storage

*   **Introduction**: How data is stored in cloud-based applications.
*   **Storage Solutions**:
    *   **Local Server Storage**: Hard drives on the server. Fast access, but not ideal for cloud app resilience/mobility.
    *   **Network Attached Storage (NAS)**: Devices with multiple hard drives (often in RAID) attached to the network. Accessed as shared drives. Can be a single point of failure. (Visual of NAS unit provided).
    *   **RAID (Redundant Array of Independent Disks)**: Data storage virtualization combining multiple physical disks for redundancy/performance.
    *   **Storage Area Network (SAN)**: Specialized, high-performance network dedicated to storage. Consists of disk arrays, switches, servers. Fault-tolerant (replication), easily extended. Typically fibre optic. Unaffected by compute network traffic.
*   **Databases**:
    *   **Relational Databases (SQL)**: Store data in tables (relations) with rows (tuples) and columns (attributes). Unique keys identify records. Tables linked by keys.
        *   SQL (Structured Query Language) for querying.
        *   RDBMS examples: MySQL, PostgreSQL.
        *   Join operation example (visual of tables and joined result).
    *   **Graph Databases**: Store data in nodes and edges (relationships). Nodes and edges can have attributes. Relationships are first-class citizens.
        *   Example diagram: Ian KNOWS Johan, Emil KNOWS Ian, etc.
    *   **NoSQL Databases**: Non-relational, handle unstructured/flexible data.
        *   Examples: MongoDB (JSON-like documents), Cassandra.
*   **Neo4j (Graph Database Example)**:
    *   Applications in E-commerce: Personalised Recommendations, Fraud Detection, Supply Chain Analysis, Customer 360 View.
    *   Usage Options: Neo4j Aura (managed cloud service), Neo4j Desktop, Docker container.
    *   Neo4j Browser/Aura UI visuals.
    *   **Cypher Query Language**:
        *   `CREATE (ee:Person {name: 'Emil', from: 'Sweden', kloutScore: 99})`
        *   `MATCH (ee:Person) WHERE ee.name = 'Emil' RETURN ee`
        *   Creating multiple nodes and relationships: `CREATE (js:Person {...}), (ir:Person {...}), (ee)-[:KNOWS {since: 2001}]->(js)`
        *   `MATCH (ee:Person)-[:KNOWS]-(friends) WHERE ee.name = 'Emil' RETURN ee, friends` (Visual of graph result).

## Typescript

*   **TypeScript Overview**:
    *   Superset of JavaScript that adds **static type checking**.
    *   Compiles to plain JavaScript, runnable in any JS environment.
    *   Benefits: Early error detection during development, improved code maintainability and readability.
    *   History: Addresses JS "novel" features (==, function scope for `var`, prototypal inheritance) by moving towards more orthodox OOP and static typing. JS was initially a "toy language" that became the "accidental language of the internet," leading to technical debt addressed over time.
*   **Basic Concepts**:
    *   **Type Annotations**: Explicitly define types (e.g., `let age: number = 30;`).
    *   **Type Inference**: TypeScript can often infer types if not explicitly annotated.
    *   **Compiling**: `tsc filename.ts` generates `filename.js`.
    *   Static Type Checking Example: `squareOf('z')` would cause a compile-time error in TS if param is `number`, but a runtime `NaN` in JS.
*   **Primitive Types**:
    *   `any`: A catch-all type; disables type checking for that variable. Use sparingly.
    *   `unknown`: Safer alternative to `any`. Requires type checking (e.g., `typeof a === 'number'`) before operations.
    *   `boolean` and Boolean Literal Types (e.g., `true` as a type: `let e: true = true;`).
    *   `number` and Number Literal Types (e.g., `let f: 26.218 = 26.218;`).
    *   `bigint` and BigInt Literal Types (e.g., `let a: 1234n;`). Note the `n` suffix.
    *   `string` and String Literal Types.
    *   `symbol`: Represents unique and immutable values. `Symbol('a')`.
    *   `null`, `undefined`, `void` (for functions not returning a value).
*   **Object Types**:
    *   Define the "shape" of an object: `let c: { d: string } = { d: 'y' };`.
    *   Enforcement: Errors if properties are missing or of wrong type.
    *   Advanced Object Types:
        *   Optional Properties: `c?: string;`.
        *   Numeric Property Names (implicitly covered by index signatures usually).
        *   Index Signatures: `[key: number]: boolean;` (allows any number of numeric keys with boolean values).
    *   `readonly` modifier: Properties cannot be reassigned after initialization.
*   **Type Aliases, Unions, and Intersections**:
    *   **Type Aliases**: Create new names for types: `type Age = number; type Person = { name: string; age: Age; };`.
    *   **Union Types (`|`)**: A value can be one of several types: `type CatOrDog = Cat | Dog;`.
    *   **Intersection Types (`&`)**: Combines multiple types into one; must have all properties of combined types: `type CatAndDog = Cat & Dog;`.
*   **Arrays and Tuples**:
    *   **Arrays**: Typed collections: `number[]` or `Array<number>`. Type inference based on initial elements.
    *   **Tuples**: Fixed-length arrays where each element has a specific type: `let b: [string, string, number] = ['Malcolm', 'Gladwell', 1963];`.
        *   Optional Elements: `[number, number?]`.
        *   Rest Elements: `[string, ...string[]]` (at least one string, followed by any number of strings).
*   **Functions**:
    *   **Parameter Types**: `function greet(name: string) {...}`.
    *   **Return Types**: `function add(a: number, b: number): number {...}`.
    *   Optional (`?`) and Default Parameters (`userId: string = 'guest'`).
    *   Rest Parameters: `function sum(...numbers: number[]): number {...}`.
    *   Function Methods (`.apply()`, `.call()`, `.bind()`).
    *   **Type Aliases for Functions**: `type Filter = <T>(array: T[], f: (item: T) => boolean) => T[];`.
    *   **Generic Types (`<T>`)**: Create reusable components/functions that can work over a variety of types.
        *   `function identity<T>(arg: T): T { return arg; }`.
        *   Generic type aliases (e.g., `Filter` above).
        *   Generic functions (e.g., `map<T, U>(...)`).
        *   `Filter1` vs. `Filter2` example: Illustrates where the generic type parameter `<T>` is bound (at definition vs. at call time).
*   **Classes**:
    *   Modern, class-based OOP in TypeScript.
    *   Basic Syntax: `class Game {}`, `class Piece {}`, `class Position {}`.
    *   Inheritance: `class King extends Piece {}`.
    *   **Constructors**: `constructor(private file: FileVal, private rank: RankVal) {}` (shorthand for declaring and initializing properties).
    *   **Access Modifiers**: `public` (default), `private` (accessible only within the class), `protected` (accessible within the class and subclasses).
    *   **Class Methods**: Functions defined within a class.
    *   **Abstract Classes and Methods**:
        *   `abstract class Piece { abstract canMoveTo(position: Position): boolean; moveTo(position: Position) {...} }`.
        *   Abstract classes cannot be instantiated directly.
        *   Abstract methods must be implemented by concrete subclasses.
    *   **Static Methods and Properties**: Belong to the class itself, not instances. `static makePieces() {}`.
    *   **Structural Typing**: TypeScript checks type compatibility based on the structure (shape) of objects, not just their explicit declarations. (Zebra/Poodle example).
    *   **Generics for Classes**: `class MyMap<K, V> { ... }`.
*   **Interfaces**:
    *   Define contracts for the shape of an object or the signature of a class.
    *   Similar to type aliases for object shapes: `interface Sushi { calories: number; salty: boolean; }`.
    *   **Interface Inheritance**: `interface Food { ... } interface Sushi extends Food { ... }`.
    *   **Declaration Merging**: Multiple interface declarations with the same name are merged into a single definition (unlike type aliases).
    *   **Implementing Interfaces**: Classes can implement interfaces: `class Cat implements Animal, Feline { ... }`. (Multiple implementations allowed).

## Next.js

*   **Next.js Overview**:
    *   React framework for building full-stack web applications (client and server).
    *   Improves initial page load, SEO, and user experience on slower devices compared to client-side React alone.
    *   Course demo website repo: `https://gitlab.com/comp315/website`.
*   **Rendering Strategies**:
    *   **Client-Side Rendering (CSR)**: React's default. Browser downloads minimal HTML + JS bundle, JS manipulates DOM. Fast re-renders, slow initial load. (React `index.html` template is minimal, with a root div for mounting).
    *   **Server-Side Rendering (SSR)**: Server generates HTML per request, browser receives full HTML + minimal JS for interactivity. Faster initial load, potentially slower re-renders if entire page re-fetches.
    *   **Hydration**: Process where client-side JavaScript makes server-rendered HTML interactive.
    *   Next.js uses SSR by default.
    *   Switching to CSR in Next.js: Add `"use client";` directive at the top of a component file.
    *   React now recommends using Next.js or similar frameworks for full-stack applications.
*   **App Router (Next.js 13+)**:
    *   Directory-based routing within the `app/` directory.
    *   **Terminology**: URL Segment (part of path delimited by `/`), URL Path (part after domain).
    *   **Folders define routes / route segments**.
    *   **Nested Routes**: Achieved by nesting folders.
    *   **Special Files (File Conventions)**:
        *   `page.js` / `page.tsx`: UI for a route segment, makes the route publicly accessible.
        *   `layout.js` / `layout.tsx`: Shared UI for a segment and its children. Root layout is required.
        *   `loading.js` / `loading.tsx`: Loading UI (wraps page/children in React Suspense).
        *   `error.js` / `error.tsx`: Error UI (wraps page/children in React Error Boundary).
        *   `global-error.js`: Catches errors in root layout.
        *   `route.js` / `route.ts`: Server-side API endpoints (Route Handlers).
        *   `template.js`: Re-rendered layout on navigation.
        *   `default.js`: Fallback UI for Parallel Routes.
    *   **Component Hierarchy**: `layout` -> `template` -> `error` -> `loading` -> `not-found` -> `page` or nested `layout`. (Diagrams provided).
    *   **Colocation**: Placing non-route files (components, styles, tests) within `app/` subdirectories. Only content from `page.js` or `route.js` is publicly addressable. (Diagram provided).
    *   **Dynamic Routes**: `[folderName]` (e.g., `app/blog/[slug]/page.tsx`). Dynamic segments are passed as `params` prop.
    *   Advanced Routing Patterns: Parallel Routes, Intercepting Routes.
*   **Project Setup**:
    *   `npx create-next-app@latest`. Interactive setup prompts for TypeScript, ESLint, Tailwind CSS, `src/` directory, App Router.
    *   Docker support can be added by including `Dockerfile` and `.dockerignore` (e.g., from Vercel examples).
    *   Directory Structure: Includes `.next/` (build output), `public/` (static assets), `src/` (or root for `app/` and `components/`), `next.config.mjs`, `package.json`.
*   **Route Handlers (`app/.../route.js` or `route.ts`)**:
    *   Create custom API endpoints accessible via HTTP.
    *   Use Web Request (`Request`, `NextRequest`) and Response (`Response`, `NextResponse`) APIs.
    *   Supported HTTP methods: `GET`, `POST`, `PUT`, `PATCH`, `DELETE`, `HEAD`, `OPTIONS`.
    *   `export const dynamic = 'force-dynamic';` for dynamic rendering.
    *   Caching: `GET` requests with `Response` object are cached by default. Opt-out by using `Request` object, other HTTP methods, dynamic functions, or Segment Config Options.
*   **Data Fetching**:
    *   **Server Components** (default in App Router): Can fetch data directly using `async/await` with `fetch`.
        *   Next.js extends `fetch` to automatically memoize requests and allow caching/revalidation configuration.
        *   Example: `async function getData() { const res = await fetch(...); return res.json(); }`.
    *   **Client Components (`"use client";`)**: Fetch data via Route Handlers or third-party libraries.
    *   **Caching with `fetch`**:
        *   Data Cache: Persistent HTTP cache on the server.
        *   Revalidation:
            *   Time-based: `fetch(url, { next: { revalidate: 3600 } })`.
            *   Segment-level revalidation: `export const revalidate = 3600;` in `page.js` or `layout.js`.
            *   On-demand: By path (`revalidatePath('/blog')`) or by tag (`revalidateTag('collection')`) in Server Actions or Route Handlers. Fetch requests can be tagged: `fetch(url, { next: { tags: ['collection'] } })`.
        *   Error handling: If revalidation fails, stale data is served, retry on next request.
    *   **Opting out of Data Caching for `fetch`**:
        *   `fetch(url, { cache: 'no-store' })` or `fetch(url, { next: { revalidate: 0 } })`.
        *   If fetch is in a Route Handler using POST.
        *   If fetch comes after usage of `headers()` or `cookies()`.
        *   If `const dynamic = 'force-dynamic'` route segment option is used.
        *   If `fetchCache` route segment option is `skip-cache`.
        *   If fetch uses `Authorization` or `Cookie` headers and there's an uncached request above it.
*   **Dynamic Functions and Dynamic Rendering**:
    *   Functions relying on request-time info (cookies, headers, URL search params).
    *   `cookies()` and `headers()`: Next.js functions to access cookies/headers in Server Components. Opts route into dynamic rendering.
    *   `searchParams` prop: Access URL query parameters. Opts component into dynamic rendering.
    *   Using dynamic functions disables caching for `fetch` requests in the same route segment unless explicitly configured.
*   **Server Actions**:
    *   Asynchronous functions executed on the server, often for form submissions and data mutations.
    *   Defined with `"use server";` directive:
        *   Inline in Server Components: At the top of the `async function`.
        *   Module-level: At the top of a separate file (e.g., `app/actions.ts`); all exports become server actions.
    *   Client Components can only import module-level Server Actions.
    *   Can be passed as props to Client Components.
    *   **Forms and Progressive Enhancement**:
        *   React extends HTML `<form>` with `action` prop to invoke Server Actions.
        *   Server Components support progressive enhancement by default (form submits even if JS disabled).
        *   Client Components queue submissions if JS isn't loaded, then submit without page refresh after hydration.
    *   **`useActionState` Hook**:
        *   React hook for updating state based on form action results.
        *   `const [state, formAction] = useActionState(actionFunction, initialState);`.
        *   Supports progressive enhancement, can show server response even before hydration.
        *   Optional third argument for permalink for non-JS redirect.
    *   Server Action Example (Invoice form): `createInvoice` server action, `FormData` object.
*   **Deploying Next.js**:
    *   `next build` generates an optimized production version.
    *   Deployment options: Vercel (creators of Next.js), self-host on Node.js server, Docker image, static HTML files.
    *   Course will use self-hosting with Docker/Kubernetes.
