# COMP315 Revision Outline

## Data Centres

*   **A Data Centre Tour**
    *   Physical appearance: External (AWS example), Internal (Google example with server racks).
    *   Key hardware:
        *   **Server Rack**: Housing for servers and networking equipment.
        *   **Server**: Individual computer units providing processing power.
        *   **Network Switch**: Connects devices within the data centre network.
    *   Cooling:
        *   **Server Cooling**: Airflow through individual servers.
        *   **Rack Cooling**: Often involves raised floors for cool air distribution from below.
        *   **Other Approaches**: Locating in cool climates, underwater data centres (e.g., Microsoft's Project Natick).
*   **Data Centre Hardware Components**
    *   **Commodity Hardware**:
        *   Definition: Relatively inexpensive, readily available ("off-the-shelf") components.
        *   Characteristics: Similar to desktop PC hardware but higher specification.
        *   Chosen for cost-effectiveness and ease of replacement.
    *   **Compute Resources**:
        *   Server components: CPUs, RAM, hard disks, network cards (no monitor, keyboard, or mouse directly attached for operation).
        *   Mounting: Typically rack-mounted.
        *   **Top-of-Rack Switch**:
            *   Connects all servers within the same rack.
            *   Connects the rack to the broader data centre network.
        *   Storage: Hard drives can be on servers or network-accessible.
    *   **Local Networks vs. The Internet**:
        *   **Local Area Networks (LANs)**: Limited geographic area (e.g., single building), typically owned by a single organization.
        *   **The Internet**: Global network of interconnected private, public, academic, business, and government networks; no single entity owns it.
    *   **Network Interface Cards (NICs)**:
        *   Function: Allow hardware components to connect to a network.
        *   Aliases: Network interfaces, network adaptors, network cards.
    *   **MAC Addresses**:
        *   Definition: Unique Media Access Control address assigned to each NIC.
        *   Assignment: Set by the manufacturer when the NIC is made.
        *   Format: Six pairs of hexadecimal digits (e.g., `00:1A:2B:3C:4D:5E`).
            *   First three pairs: **Organizationally Unique Identifier (OUI)** (identifies the manufacturer).
            *   Last three pairs: **NIC-Specific Identifier** (device-specific).
    *   **Network Switches**: Connect devices *within* a single computer network.
    *   **Routers**: Connect *multiple* networks together and direct traffic *between* them.
    *   **Firewalls**: Network security devices at the boundary of a network, monitoring and filtering incoming/outgoing traffic based on predefined rules.

## Server Software

*   **Operating Systems (OS)**
    *   Function: Manage computer hardware and software resources, provide an interface for programs.
    *   Cloud Server OS: Predominantly **Linux**.
    *   **Linux**:
        *   Free and open-source family of OS built on a common kernel.
        *   Distributions: RHEL (Red Hat Enterprise Linux) is common for cloud servers.
    *   **Linux Kernel**:
        *   Core of the Linux OS.
        *   Manages hardware, provides essential services (process management, memory management, device drivers).
    *   **Kernel Space vs. User Space**:
        *   **Kernel Space**: Privileged mode where the kernel operates with direct hardware access.
        *   **User Space**: Restricted mode where user applications run, accessing hardware via kernel system calls.
    *   **Root User**: Special account with the highest privileges in the system (operates in user space but can perform kernel-level operations via system calls). Use with caution.
*   **Virtual Machines (VMs)**
    *   **Virtualisation**: Creating virtual versions of physical components (servers, storage, etc.).
    *   **Hypervisor**: Software layer enabling VM creation and management.
        *   **Type 1 (Bare-Metal)**: Runs directly on host hardware (e.g., VMware ESXi, Microsoft Hyper-V). Higher performance. Tech Stack: App -> VM -> Hypervisor -> Hardware.
        *   **Type 2 (Hosted)**: Runs on top of a host OS (e.g., VMware Workstation, VirtualBox). Easier setup.
    *   Benefits of Virtualisation: Efficiency, cost savings, flexibility, isolation.

## HTML and CSS

*   **Core Web Technologies**:
    *   **HTML (HyperText Markup Language)**: Structures web page content.
    *   **CSS (Cascading Style Sheets)**: Styles the appearance and layout of HTML content.
    *   **JavaScript**: Adds interactivity and dynamic behavior.
*   **HTML**:
    *   Tags and Elements: `<html>`, `<head>`, `<body>`, `<h1>`, `<p>`, `<div>`, `<input>`, `<table>`, etc.
    *   Attributes: `class`, `id`, `style` provide additional info/hooks for CSS and JS.
*   **DOM (Document Object Model)**:
    *   Tree-like representation of an HTML document's structure.
    *   Allows JavaScript to dynamically access and manipulate content, structure, and style.
*   **CSS**:
    *   Selectors and Properties: Target HTML elements to apply styles (e.g., `font-family`, `color`, `background-color`).
    *   Linking CSS: External stylesheets (`<link href="style.css">`), internal styles (`<style>`), inline styles (`style` attribute).
*   **Tailwind CSS**:
    *   Utility-first CSS framework.
    *   Apply styling directly in HTML using predefined classes (e.g., `bg-blue-500`, `text-white`, `p-4`, `font-bold`).
    *   Removes the need to write custom CSS for many common styling tasks.

## Javascript

*   **Running JavaScript**: Browser console, Node.js (command line).
*   **JavaScript Basics**:
    *   **Primitive Types**: `Undefined`, `Null`, `Boolean`, `Number`, `String`, `Symbol`, `BigInt`.
    *   **Undefined vs. Null**: `undefined` = unassigned, `null` = intentional absence of value.
    *   **Expressions vs. Statements**: Expressions resolve to a value; statements perform actions.
    *   **`let`, `const`, `var`**: Variable declaration. `let`/`const` are block-scoped; `var` is function-scoped (avoid `var`).
    *   **Truthiness/Falsiness**: How values behave in boolean contexts (e.g., `0`, `""`, `null`, `undefined`, `NaN` are falsy).
        *   Gotchas: `[]` and `{}` are truthy; `"0"` is truthy.
    *   **Equality**: `==` (loose, type coercion) vs. `===` (strict, no coercion - preferred).
    *   **Template Literals**: Backticks (`` ` ``) for strings with embedded expressions `${...}`.
*   **Compound Data Types**:
    *   **Arrays**: Ordered lists (e.g., `let arr = [1, 'two'];`). Methods: `push`, `pop`, `slice`, `splice`, `concat`.
    *   **Objects**: Collections of key-value properties (e.g., `let obj = { name: "Alice", age: 30 };`).
    *   **Methods and `this`**: Functions as object properties. `this` context varies (method call, function call, arrow function).
    *   **Strict Mode (`"use strict";`)**: Catches common errors, changes `this` behavior in functions.
    *   **Object Destructuring**: `const { name, age } = user;`.
    *   **Spread Operator (`...`)**: For arrays (`[...arr1, newItem]`) and objects (`{...obj1, newProp: val}`).
    *   **Prototype Chains**: Mechanism for inheritance. Objects inherit properties/methods from their prototype. `Object.create()`.
*   **Conditionals and Loops**:
    *   `if/else if/else`, ternary operator.
    *   `switch`.
    *   `for`, `for...of` (for iterables), `for...in` (for object keys).
    *   `while`, `do...while`.
*   **Functions**:
    *   Declarations, expressions, arrow functions.
    *   Rest Parameters: `function sum(...args) {}`.
*   **Classes (ES6)**: Syntactic sugar over prototypal inheritance. `class MyClass extends AnotherClass { constructor() { super(); } method() {} }`.
*   **JSON (JavaScript Object Notation)**:
    *   Text format for data interchange.
    *   Syntax: Objects `{}`, arrays `[]`, strings in double quotes, numbers, booleans, `null`.
    *   `JSON.stringify()`: JS object to JSON string.
    *   `JSON.parse()`: JSON string to JS object.
*   **YAML (YAML Ain’t Markup Language)**:
    *   Human-readable data serialization, often used for configuration.
    *   Syntax: Indentation-based. Key-value pairs, lists (`- item`).
    *   Supports comments (`#`).

## Security

*   **Vulnerabilities and the Zero-Day Problem**:
    *   Absolute security is unattainable.
    *   **Patch Cycle**: Discovery -> Patch -> Installation.
    *   **Zero-Day Vulnerability**: A flaw exploited before a patch is available.
*   **Host Defences**:
    *   **Principle of Least Privilege (PoLP)**: Grant only necessary permissions.
    *   **Sandboxing**: Running programs in restricted environments.
    *   **Discretionary Access Control (DAC)**: Default in Linux. Permissions based on user/owner discretion.
        *   File Permissions: `rwx` for owner, group, others (e.g., `755`). `chmod`, `sudo`.
    *   **Mandatory Access Control (MAC)**: OS-enforced policies, admin-defined.
*   **SELinux (Security-Enhanced Linux)**:
    *   MAC implementation for Linux.
    *   Modes: Enforcing, Permissive, Disabled.
    *   **Labelling System**: Processes and objects (files, ports) have labels.
    *   **Policies**: Rules define allowed interactions between labels.
    *   **Type Enforcement**: Primary model. Access based on type labels (e.g., `httpd_t` process can access `httpd_sys_content_t` files).
    *   **Multi-Category Security (MCS)**: Adds categories to labels for finer-grained separation between instances of the same type.
    *   **Multi-Level Security (MLS)**: Based on data sensitivity levels (clearances) and dominance rules.

## Containers

*   **Overview**:
    *   Lightweight alternative to VMs for application encapsulation.
    *   Share host OS kernel, providing process-level isolation.
    *   Tools: Docker, PodMan, Kubernetes.
*   **Tech Stack**: App -> Container -> Host OS Kernel -> Hardware. (Can also run on VMs).
*   **Docker**:
    *   **Images**: Read-only templates for creating containers. Built from **Dockerfiles**.
    *   **Dockerfiles**: Instructions to build an image (`FROM`, `RUN`, `COPY`, `CMD`, `EXPOSE`).
    *   **Layers**: Images are composed of stacked, read-only layers.
    *   **Docker Hub**: Public registry for Docker images.
    *   CLI Commands: `docker pull`, `docker run`, `docker build`, `docker ps`, `docker stop`, `docker rm`, `docker rmi`.
*   **Containers and the Linux Kernel**:
    *   **Namespaces**: Isolate resources (PID, NET, MNT, UTS, IPC, USER).
    *   **Control Groups (cgroups)**: Limit and monitor resource usage (CPU, memory).
    *   **Union File Systems**: Layered file systems for containers (efficient storage and sharing).
*   **Kubernetes (K8s) - Introduction**:
    *   Container orchestration system. Automates deployment, scaling, management.
    *   "OS for data centres."
    *   History: Google (Borg/Omega experience), open-sourced, CNCF.
    *   **CRI (Container Runtime Interface)** & **OCI (Open Container Initiative)**: K8s uses CRI to interact with OCI-compliant runtimes like `containerd`.
    *   **Microservices**: Architectural style favored by containerization. Application as a collection of small, independent services.

## Ansible I

*   **Configuration as Code (CaC)**: Manage configurations using code (Ansible).
*   **Agentless Architecture**: No agents on managed nodes; uses SSH.
*   **Inventory**: Defines hosts and groups (YAML/INI). `ansible_host`, `ansible_connection`.
*   **Playbooks**: YAML files defining desired state and tasks.
    *   **Idempotency**: Operations only make changes if needed.
    *   Structure:
        *   **Plays**: Target hosts, `become` for privilege escalation.
        *   **Tasks**: Actions performed by modules.
        *   **Modules**: Units of code performing specific actions (e.g., `yum`, `service`, `file`, `ping`, `debug`).
        *   Conditionals: `when: condition`.
        *   Variables: `register: var_name` (capture task output). `{{ var_name }}` for interpolation.
        *   Loops: `loop: [...]`, `loop_control: label: "{{ item }}"`.
*   **Ansible Variables**:
    *   Defined in playbooks (`vars:`), inventory, variable files.
    *   **Facts**: System information automatically gathered by Ansible. `ansible_facts`.
*   **Required Reading**: Ansible: Up and Running.

## Hosting

*   **Web Servers**: Host and serve web content (e.g., Apache, NGINX).
*   **Proxies**:
    *   **Forward Proxy**: Client -> Proxy -> Internet. Use cases: caching, filtering, anonymity for clients.
    *   **Reverse Proxy**: Internet -> Proxy -> Backend Servers. Use cases: load balancing, SSL termination, security, caching for servers.
*   **Apache HTTP Server**:
    *   Configuration: `httpd.conf`, `DocumentRoot`.
    *   HTTPS Setup:
        *   SSL/TLS certificates (CA-signed or self-signed with `openssl`).
        *   Apache SSL configuration (`httpd-ssl.conf`, enabling SSL modules).
        *   Dockerfile updates to include certs, keys, SSL config, and expose port 443.
*   **NGINX**: Often used as a reverse proxy.
    *   Configuration: `nginx.conf` (`upstream` block for backend servers, `server` block with `listen` and `proxy_pass`).
    *   Docker setup for NGINX reverse proxying to an Apache backend. Requires Docker network.

## Storage

*   **Storage Solutions**:
    *   **Local Server Storage**: Fast, but single point of failure for cloud apps.
    *   **Network Attached Storage (NAS)**: RAID-based, network-accessible shared drives.
    *   **Storage Area Network (SAN)**: Dedicated, high-performance network for block-level storage.
*   **RAID**: Redundant Array of Independent Disks.
*   **Databases**:
    *   **Relational Databases (SQL)**: Tables, rows, columns, primary/foreign keys, SQL queries, Joins (e.g., MySQL, PostgreSQL).
    *   **Graph Databases**: Nodes, edges, properties. Relationships are first-class citizens (e.g., Neo4j with Cypher query language).
    *   **NoSQL Databases**: Non-relational, flexible schemas (e.g., MongoDB - document, Cassandra - wide-column).
*   **Neo4j**:
    *   Graph database, uses Cypher.
    *   Nodes: `(alias:Label {property: value})`.
    *   Relationships: `-[alias:TYPE]->`.
    *   CRUD: `CREATE`, `MATCH`, `WHERE`, `RETURN`, `DELETE`.

## Typescript I & II

*   **TypeScript Overview**: Superset of JavaScript adding static types. Compiles to JS.
*   **Benefits**: Early error detection, improved code quality and maintainability.
*   **Basic Types**: `number`, `string`, `boolean`, `null`, `undefined`, `any`, `unknown`, `void`, `never`, `object`.
*   **Type Annotations & Inference**: `let name: string = "Alice";` vs `let name = "Alice";` (inferred).
*   **Literal Types**: Specific values as types (e.g., `type Status = "success" | "error";`).
*   **`any` vs. `unknown`**: `any` bypasses type checking; `unknown` is type-safe (requires type assertion/narrowing).
*   **Object Types**: Define shape of objects: `{ id: number; name: string; }`.
    *   Optional Properties: `email?: string;`.
    *   Readonly Properties: `readonly id: number;`.
    *   Index Signatures: `[key: string]: any;`.
*   **Arrays & Tuples**:
    *   Arrays: `number[]` or `Array<number>`.
    *   Tuples: Fixed-size arrays with specific types per element: `[string, number]`.
*   **Functions**:
    *   Parameter and return type annotations: `function add(a: number, b: number): number { ... }`.
    *   Optional (`?`) and default parameters.
    *   Rest parameters: `(...args: number[])`.
*   **Type Aliases**: `type UserID = string | number;`.
*   **Union Types (`|`)**: Value can be one of several types.
*   **Intersection Types (`&`)**: Value must have all properties of combined types.
*   **Generics (`<T>`)**: Reusable components/functions that work with various types.
    *   `function identity<T>(arg: T): T { return arg; }`.
    *   Generic classes, interfaces, type aliases.
*   **Classes**:
    *   Syntax: `class Person { constructor(public name: string) {} }`.
    *   Inheritance: `class Employee extends Person { ... }`.
    *   Access Modifiers: `public`, `private`, `protected`.
    *   Abstract Classes and Methods: `abstract class ...`, `abstract method()`.
    *   Static Members: `static count: number;`.
    *   Structural Typing: Compatibility based on shape, not explicit declaration.
*   **Interfaces**: Define contracts for object shapes or class implementations.
    *   `interface Point { x: number; y: number; }`.
    *   Can extend other interfaces: `interface ColoredPoint extends Point { color: string; }`.
    *   Classes can implement interfaces: `class MyPoint implements Point { ... }`.
    *   Declaration Merging: Interfaces with the same name are merged.

## Ansible II

*   **Variable Directories**: `group_vars/` and `host_vars/` for organizing variables.
*   **Ansible Vault**: Encrypt sensitive data (passwords, API keys) in variable files.
    *   `ansible-vault create/edit/view/encrypt/decrypt`.
    *   `--ask-vault-pass` when running playbooks.
*   **Password Hashing**: `{{ my_password | password_hash('sha512') }}`.
*   **Everything as Code (EaC)**:
    *   Managing all aspects of a software system (infra, config, build, deploy, monitoring) as code.
    *   **Configuration as Code (CaC)**: Ansible's primary domain.
    *   **Infrastructure as Code (IaC)**: Provisioning infra with code (e.g., Terraform, Ansible can also do this).
    *   Declarative vs. Imperative: Desired state vs. specific commands.
*   **Anything as a Service (XaaS)**:
    *   **IaaS**: Infrastructure (VMs, storage, network).
    *   **PaaS**: Platform (e.g., Kubernetes, Heroku).
    *   **SaaS**: Software (e.g., Gmail, Office 365).

## Kubernetes I, II, III, IV, V, VI

*   **Core Concepts**:
    *   **Cluster**: Set of nodes (machines).
    *   **Nodes**: Worker machines running applications.
        *   **Control Plane Nodes**: Manage the cluster.
        *   **Worker Nodes**: Run application containers.
    *   **Pods**: Smallest deployable unit; one or more containers sharing storage/network.
    *   **Deployments**: Manage stateless applications; declarative updates, replicas, rollbacks.
    *   **Services**: Abstract way to expose an application running on a set of Pods (stable IP/DNS).
        *   Types: `ClusterIP` (internal), `NodePort` (exposes on node's IP and port), `LoadBalancer` (integrates with cloud provider LB).
    *   **Namespaces**: Virtual clusters within a physical cluster for isolation.
    *   **Labels and Selectors**: Key-value pairs for organizing and selecting objects.
    *   **Manifests**: YAML/JSON files defining K8s objects (declarative approach). `kubectl apply -f <manifest.yaml>`.
*   **Control Plane Components**:
    *   **API Server (`kube-apiserver`)**: Front-end, exposes K8s API (RESTful).
    *   **etcd**: Distributed key-value store for cluster state.
    *   **Scheduler (`kube-scheduler`)**: Assigns Pods to Nodes.
    *   **Controller Manager (`kube-controller-manager`)**: Runs controller processes (e.g., Deployment controller, ReplicaSet controller).
*   **Worker Node Components**:
    *   **Kubelet**: Agent on each node, ensures containers are running in a Pod as specified.
    *   **Kube-proxy**: Network proxy, maintains network rules on nodes (Service routing).
    *   **Container Runtime**: Software to run containers (e.g., `containerd`, Docker).
*   **`kubectl`**: Command-line tool for interacting with K8s clusters.
    *   Common commands: `get`, `describe`, `apply`, `delete`, `expose`, `scale`, `rollout`.
*   **Minikube**: Tool for running a single-node K8s cluster locally.
*   **High Availability (HA)**: Achieved through replication of control plane components and application Pods, often across Availability Zones (AZs).
*   **Networking**:
    *   Pod-to-Pod communication.
    *   Service discovery.
    *   Overlay Networks (e.g., Calico): Provide networking for Pods across nodes.
*   **Ansible for Kubernetes Setup**:
    *   Automating cluster provisioning: Disabling SELinux/swap, configuring firewalls, kernel parameters, hostnames.
    *   Installing container runtime (`containerd`).
    *   Installing K8s packages (`kubeadm`, `kubelet`, `kubectl`).
    *   Initializing control plane (`kubeadm init`).
    *   Joining worker nodes (`kubeadm join`).
    *   Installing an overlay network (Calico).
*   **Service Mesh (Istio)**:
    *   Dedicated infrastructure layer for managing service-to-service communication.
    *   Components: Data Plane (Envoy sidecar proxies), Control Plane (Istiod).
    *   Features: Traffic management (routing, canary releases), security (mTLS), observability (metrics, tracing with Kiali, Grafana, Prometheus).
    *   Installation: `istioctl install`. Sidecar injection via namespace labeling.
*   **CI/CD for Kubernetes**:
    *   **Git**: Version control for application code and K8s manifests.
    *   **GitLab CI**: Continuous Integration (build Docker images, run tests). Configured via `.gitlab-ci.yml`.
    *   **ArgoCD**: Continuous Delivery/GitOps tool. Synchronizes K8s cluster state with Git repository (manifests).
        *   Application YAML: Defines ArgoCD application (source repo, path, destination, sync policy).
        *   Deployment/Service YAMLs: Stored in Git, define K8s resources for the app.

## Next.js I, II, III

*   **Next.js Overview**: React framework for building full-stack web applications.
    *   Features: Server-Side Rendering (SSR), Static Site Generation (SSG), Client-Side Rendering (CSR), file-system routing, API routes.
*   **Rendering Strategies**:
    *   **Client-Side Rendering (CSR)**: JS renders content in browser. Default for basic React.
    *   **Server-Side Rendering (SSR)**: HTML generated on server per request. Default in Next.js Pages Router for `getServerSideProps`.
    *   **Static Site Generation (SSG)**: HTML generated at build time. Default for Next.js pages without server-side data fetching.
    *   **Hydration**: Process of making server-rendered HTML interactive in the browser using client-side JS.
    *   `"use client";` directive: Marks a component and its imports as client-side, enabling CSR and hooks like `useState`, `useEffect`.
*   **App Router**:
    *   Directory-based routing within the `app/` directory.
    *   **Folders** define routes.
    *   **Special Files**:
        *   `page.js` / `page.tsx`: UI for a route segment.
        *   `layout.js` / `layout.tsx`: Shared UI for a segment and its children.
        *   `loading.js` / `loading.tsx`: Loading UI using React Suspense.
        *   `error.js` / `error.tsx`: Error UI using React Error Boundaries.
        *   `route.js` / `route.ts`: API endpoints (Route Handlers).
    *   **Dynamic Routes**: `[folderName]` (e.g., `app/blog/[slug]/page.tsx`). Params passed to page.
    *   **Component Hierarchy**: `layout` -> `template` -> `error` -> `loading` -> `not-found` -> `page` or nested `layout`.
*   **Data Fetching**:
    *   **Server Components** (default in App Router): Can fetch data directly using `async/await` with `fetch`.
    *   **Client Components**: Fetch data via Route Handlers or third-party libraries (e.g., SWR, React Query).
    *   **`fetch` API in Next.js**: Extended for caching and revalidation on the server.
        *   **Caching**: Automatic for `fetch` in Server Components. Data Cache.
        *   **Revalidation**:
            *   Time-based: `fetch(..., { next: { revalidate: seconds } })` or `export const revalidate = seconds;` in segment.
            *   On-demand: `revalidateTag(tag)` or `revalidatePath(path)` in Server Actions or Route Handlers.
        *   Opting out of caching: `cache: 'no-store'`, dynamic functions (`cookies()`, `headers()`), POST in Route Handlers.
*   **Route Handlers (`route.js`/`route.ts`)**:
    *   Create API endpoints. `export async function GET(request: Request) { ... }`.
    *   Use Web Request and Response APIs (`NextRequest`, `NextResponse` for extensions).
*   **Server Actions**:
    *   Asynchronous functions executed on the server, often for form submissions and data mutations.
    *   Defined with `"use server";` directive (inline in Server Components or module-level).
    *   Can be invoked from forms: `<form action={myServerAction}>`.
    *   Progressive Enhancement: Forms work even if JS is disabled (for Server Components).
    *   `useActionState` hook: Manage form state based on action results, supports progressive enhancement.
*   **Dynamic Functions**: `cookies()`, `headers()`, `searchParams` prop. Opt route into dynamic rendering.
*   **Project Setup**: `npx create-next-app@latest`. Options for TypeScript, Tailwind CSS, App Router.
*   **Deployment**: `next build` creates production-ready app. Deploy to Vercel, Node.js server, Docker.
