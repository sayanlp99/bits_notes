### Full Stack Application Development

---

### Website
- **Definition**: A group of interlinked web pages with a single domain name, hosted on a web server, accessible via the internet.
- **Use Cases**: Portfolios, personal blogs, informational websites, small business websites with minimal content updates, landing pages, and temporary promotions.

### Web Application
- **Definition**: An application program stored on a remote server, delivered over the internet, and accessed through a web browser.
- **Common Examples**: E-commerce shops, webmail, social networking sites.

---

### Application Types

#### Native Apps
- **Definition**: Developed for a specific platform or operating system and installed directly onto the device.
- **Pros**: Offline usage, direct hardware access, device-specific gestures, full feature access, app store approval, improved security.
- **Cons**: Higher development and maintenance costs, tedious app store approval process, needs updates.
- **Technologies**:
  - **iOS**: Swift, Objective-C, Xcode (Example: Instagram)
  - **Android**: Java, Kotlin, Android Studio (Example: WhatsApp)

#### Web Apps
- **Definition**: Internet-enabled applications accessible via a web browser, written in HTML, CSS, JavaScript.
- **Pros**: Instant accessibility, easier updates and maintenance, discoverable via search engines, cost-effective.
- **Cons**: Limited device feature access, browser variations, challenging stable performance across devices, not listed in app stores, unavailable offline.
- **Technologies**: HTML, CSS, JavaScript, React, Angular, Vue.js (Example: Google Docs)

#### Progressive Web Applications (PWAs)
- **Definition**: Built using web technologies, can be installed on devices, offering offline and background operations.
- **Technologies**: HTML, CSS, JavaScript, Workbox, Lighthouse, Service Workers, Web App Manifests.

#### Hybrid Apps
- **Definition**: Combine elements of native and web applications, built using web technologies but run inside a native container.
- **Pros**: No need for a web browser, access to device’s internal APIs and hardware, single codebase.
- **Cons**: Slower than native apps, reliant on third-party platforms, limited customization support.
- **Technologies**: HTML, CSS, JavaScript, Ionic, Apache Cordova, PhoneGap.

#### Cross-Platform Applications
- **Definition**: Developed to run on multiple devices, ensuring multi-platform compatibility.
- **Pros**: Cost-effective, code reusability, larger audience reach.
- **Cons**: Slower performance than native apps.
- **Technologies**: React Native, Flutter, Xamarin (Examples: Facebook, Google Ads, Microsoft Outlook).

---

### Cloud-Native Applications

#### Definition
- **Cloud-native** is an approach to developing, deploying, and running applications using modern methods and tools.
- **CNCF Definition**: Technologies that empower organizations to build and run scalable applications in modern environments like public, private, and hybrid clouds. Examples include containers, service meshes, microservices, immutable infrastructure, and declarative APIs.

#### Cloud-Enabled Solutions
- **Monolithic Application**: Traditional software design where the entire application is a single, self-contained unit.
  - **Characteristics**: Single codebase, tight coupling, single deployment unit, centralized database, development and scaling challenges, longer development cycles, limited fault isolation.
- **Cloud-Based Application**: Existing app shifted to the cloud, not fully leveraging cloud potential. Issues include lack of scalability, less automation, longer time to market.
- **Cloud-Native Applications**: Designed to run on cloud architecture, leveraging automation and scalability.

#### Comparison: Cloud Native vs. Traditional Applications
- **Cloud-Enabled**: Developed for traditional data centers, later modified for cloud environments.
- **Cloud-Native**: Built for the cloud, scalable, platform-agnostic, composed of microservices.

---

### Pillars of Cloud-Native Applications

#### Building Blocks
1. **Microservices**:
   - Architectural approach where applications are a collection of small services.
   - Each service implements business capabilities, runs independently, and communicates via HTTP APIs or messaging.
2. **Containers**:
   - Offer efficiency and speed compared to standard VMs.
   - OS-level virtualization allows isolated containers with unique file systems and resource quotas.
   - Low overhead and high packing density make containers ideal for deploying microservices.
3. **DevOps**:
   - Collaboration between software developers and IT operations for high-quality software delivery.
   - Promotes rapid, frequent, and consistent building, testing, and releasing.
4. **Continuous Delivery**:
   - Automation for shipping small software batches to production constantly.
   - Ensures reliable releases, frequent delivery, and faster user feedback.

#### Advantages
- Reduced time to market
- Ease of management
- Scalability and flexibility
- Reduced cost

---

### Serverless Applications

#### Definition
- **Serverless Architecture**: Allows developers to build and run services without managing infrastructure. Cloud providers handle provisioning, scaling, and managing infrastructure.

#### Function as a Service (FaaS)
- Application code is written as discrete functions performing specific tasks triggered by events.
- Cloud provider executes the function, abstracting the execution process from developers.
- **Examples**:
  - **AWS**: AWS Lambda
  - **Microsoft Azure**: Azure Functions
  - **Google Cloud**: Cloud Functions

#### Serverless Benefits and Drawbacks
- **Benefits**:
  - Reduced operational cost
  - Easier operational management
  - Scalability
- **Drawbacks**:
  - Loss of control
  - Vendor lock-in
  - Multitenancy problems
  - Security concerns

#### AWS Serverless Offerings
- **AWS Lambda**: Run code without provisioning or managing servers.
- **AWS Fargate**: Serverless compute engine for containers.
- **Amazon API Gateway**: Fully managed service for creating, publishing, maintaining, monitoring, and securing APIs at any scale.

#### Reference Architecture: Web Application
- **General-purpose, event-driven web application backend**:
  - **AWS Lambda** and **Amazon API Gateway** for business logic
  - **Amazon DynamoDB** as the database
  - **Amazon Cognito** for user management
  - **AWS Amplify Console** for hosting static content
  
  <img src="1.png" alt="1" width="350px" height="350px">

---
### Layered Pattern
- **Context**: Separation of concerns.
- **Problem**: Ensuring that system modules are independently developed and maintained, promoting portability, modifiability, and reuse.
- **Solution**: Dividing software into units called layers, where each layer is a cohesive set of services.
  - **Interaction**: Strict unidirectional ordering.
  - **Interface**: Each partition is exposed through an interface.

---

### Web Application Architecture
- **Layered Architecture**: Fundamental structure for web applications.
  - **Two-Layer Systems**: Client-server systems where the client holds the user interface and application code, and the server hosts a relational database.
  - **Three-Tier Architecture**:
    - **Presentation (UI)**: User interface components.
    - **Business Logic**: Core functionality and business rules.
    - **Data Access**: Interaction with the database.

![2](2.png)

---

### Ensuring Clear Separation of Concerns
- **Scenario 1**: Highlight products with over 10% increase in sales.
  - **Method 1**: Embed logic directly into the presentation layer.
  - **Method 2**: Use a method in the domain layer to indicate improved sales, then call this method from the presentation layer.
- **Scenario 2**: Adding a command-line interface to a web application.
  - **Method**: Avoid duplicating functionality by properly separating layers, ensuring domain logic does not leak into the presentation.

---

### N-Tier Web Application
- **Structure**: 
  - Client (Browser)
  - Web Server
  - Application Server
  - Database (DB)
- **Characteristics**:
  - Independence of each tier.
  - Security, performance, and availability optimizations.

![3](3.png)

---

### Service-Based Web Application
- **Components**:
  - REST APIs
  - Third-Party APIs
  - Database
- **Architecture**: Similar to N-Tier but emphasizes RESTful communication.

![6](6.png)

---

### Monolithic Application
- **Definition**: Deployed as a single, self-contained unit (e.g., a Java WAR file).
- **Challenges**: Scalability issues and the need to redeploy the entire application for changes.

---

### Service-Oriented Architecture (SOA)
- **Definition**: Integrates business functionalities as services.
- **Characteristics**:
  - Loosely coupled and autonomous services.
  - Adheres to the Single Responsibility Principle.
- **SOA-Based Web Application**:
  - Client (Browser)
  - Web Services
  - Enterprise Service Bus (ESB)
  - Database (DB)

![4](4.png)

---

### Microservice Architecture
- **Characteristics**:
  - Composed of small, independent services.
  - Implements single business capabilities.
  - Loosely coupled, communicating via API contracts.
  - Built by focused development teams.
- **Complexities**: Requires mature DevOps culture and management but results in higher release velocity and resilience.

![5](5.png)

---

### Application Programming Interface (API)
- **Definition**: A software intermediary that allows two applications to communicate.
- **Types**:
  - **Public API**: External access to assets (e.g., Twitter API, Google Maps API).
  - **Private API**: Internal use for productivity and service-oriented architecture.
- **Paradigms**:
  - Request-Response APIs (e.g., REST, RPC, GraphQL).
  - Event-Driven APIs.

---

### Model-View-Controller (MVC) Pattern
- **Definition**: Divides application logic into three interconnected components: Model, View, and Controller.
  - **Model**: Manages data-related logic and interacts with the database.
  - **View**: User interface, communicates with the controller, and renders data.
  - **Controller**: Handles user input, processes requests, and manages data flow to the view.
- **Example**:
  - Routes: `/users/profiles/:id`
  - Controller: Fetches user profile and renders the view.
  - Model: Queries the database for user data.
  - View: Displays user profile information.

---

### Model-View-Presenter (MVP)
- **Definition**: The view is passive and routes user commands to the presenter.
- **MVC Variant**: Similar to MVC but with a focus on separation of presentation logic.

---

### Model-Template-View (MTV)
- **Definition**: Similar to MVC but with a distinct template component.
  - **Model**: Interface for data.
  - **Template**: Presentation layer, containing static or dynamic HTML.
  - **View**: Executes business logic and interacts with the model, rendering the template.

---

### Web Application

### **1. Client-Server Pattern**
- **Context:** Shared resources and services accessed by multiple clients.
- **Problem:** Managing shared resources efficiently while promoting modifiability and reuse.
- **Solution:** Clients send requests for services to servers, which manage and provide these services. Some components can act as both clients and servers.

**Key Points:**
- **Request-Response Model:** Clients request services, and servers respond.
- **Server:** Provides services/resources.
- **Client:** Requests services/resources.
  
**Benefits:**
- **Higher Security:** Centralized control improves security.
- **Centralized Data Access:** Data is managed centrally, making it easier to update and control.
- **Ease of Maintenance:** Centralized systems are easier to maintain than distributed ones.

### **2. Variants of Client-Server Pattern**
- **Peer-to-Peer (P2P) Applications:** Each node acts as both a client and server.
- **Application Servers:** Provide services to client applications.
- **Asynchronous Requests:** Clients don’t block while waiting for data.
- **Server-Initiated Actions:** Servers can initiate actions on clients in some scenarios.
  ![7](7.png)

### **3. Traditional vs. Modern Web Applications**
- **Traditional Web Application (Three-Tier Architecture):**
  - **Client Tier:** User interface (UI) in the browser (HTML, CSS, JavaScript).
  - **Server Tier:** Web server handles business logic.
  - **Data Tier:** Database stores data.
  ![8](8.png)
- **Modern Web Application:**
  - **AJAX:** Enables asynchronous updates without reloading the page.
  - **JSON:** Lightweight data format for efficient data exchange.
  ![9](9.png)
### **4. Front-End Responsibilities**
- **User Interface Design:** HTML, CSS, JavaScript, and frameworks like React, AngularJS, or Vue.js.
- **Asynchronous Request Handling:** Using AJAX.
- **Single-Page Applications:** Focus on smooth user experience without full page reloads.
- **Responsive Web Design:** Ensuring compatibility across different devices and browsers.

### **5. Back-End Responsibilities**
- **Software Architecture:** Designing the application's structure.
- **Application Logic:** Core functionalities and processing.
- **Database Management:** Handling data storage and retrieval.
- **Security:** Authentication, authorization, and ensuring data security.

### **6. Understanding URLs**
- **URL Components:**
  - **Scheme:** Protocol used (e.g., HTTP, HTTPS).
  - **Host Name:** Domain name or IP address.
  - **Port Number:** Specifies the exact server application.
  - **Path:** The specific resource on the server.
  - **Query Parameters:** Additional data for processing.
  - **Fragment:** Refers to a specific section of the webpage.

### **7. Domain Name System (DNS)**
- **Function:** Translates domain names (like google.com) into IP addresses.
- **DNS Hierarchy:**
  - **Root Server:** First step in name resolution.
  - **TLD Server:** Top-Level Domain servers (e.g., .com, .org).
  - **Authoritative Name Server:** Final server that resolves the domain name.

**Importance of DNS:**
- **Eliminates the Need to Remember IP Addresses:** Easier for users to access websites.

  ![10](10.png)

### **8. Content Delivery Network (CDN)**
- **Purpose:** Improves website load times by caching content closer to users.
- **Benefits:**
  - **Improved Load Times:** Content is delivered faster.
  - **Reduced Bandwidth Costs:** Efficient data management reduces costs.
  - **Increased Availability:** Content is redundant across multiple locations, ensuring availability.
  - **Enhanced Security:** Provides additional security layers.

### **9. Client-Side Rendering (CSR)**
- **Process:** Web content is rendered on the client-side, in the user's browser.
- **Benefits:** 
  - **Improved Performance:** Faster interactions as only necessary data is reloaded.
  - **Rich User Experience:** Smooth and responsive UI.
  ![11](11.png)

### **10. Server-Side Rendering (SSR)**
- **Process:** Web content is rendered on the server before being sent to the client.
- **Benefits:**
  - **Better SEO:** Search engines can crawl content more effectively.
  - **Faster Initial Load:** Content is ready to display as soon as it arrives at the client.
  - **Improved Accessibility:** Works better on low-powered devices.

### **11. Static Site Generation (SSG)**
- **Definition:** Generates static HTML files ahead of time and serves them to users.
- **Benefits:**
  - **High Performance:** Pre-built pages load quickly.
  - **SEO-Friendly:** Search engines can index static pages easily.
  
- **Limitations:**
  - **Not Suitable for Real-Time Data:** Static content can’t reflect live updates.
  
**Popular Tools:** Jekyll, Hugo, Gatsby.

### **12. Client-Side Programming**
- **Technologies:**
  - **HTML/CSS:** Structure and style web content.
  - **JavaScript (JS):** Adds interactivity to web pages.
  - **Frameworks:** Angular, React, Vue for creating dynamic web applications.

### **13. Server-Side Programming**
- **Technologies:**
  - **Languages:** JavaScript (Node.js), Python (Django, Flask), Ruby (Rails), Java (Spring), PHP (Laravel).
  - **Databases:** MySQL, PostgreSQL (Relational), MongoDB (NoSQL).
  - **Caching:** Memcached, Redis to manage high traffic and reduce database load.
  
**Server Management:**
- **Web Servers:** Apache, Nginx handle client requests.
- **Load Balancers:** Distribute incoming traffic across multiple servers.

### **14. Example Tech Stacks**
- **MEAN/MERN/MEVN Stack:**
  - **MongoDB:** NoSQL database.
  - **Express.js:** Web framework for Node.js.
  - **Angular/React/Vue.js:** Frontend frameworks.
  - **Node.js:** JavaScript runtime for server-side scripting.

- **Python Stack:**
  - **Flask/Django:** Web frameworks.
  - **SQLAlchemy:** ORM for database management.
  - **Django REST Framework:** For building APIs.

---

### Web Protocols: (HTTP)

#### 1. **Introduction to HTTP**
- **HTTP (HyperText Transfer Protocol)**: 
  - A stateless request-response protocol used for distributed and collaborative hypermedia information systems.
  - Operates in a client-server model.
  - Each HTTP communication includes:
    - **Header**: Contains information about the communication.
    - **Body**: Contains the data of the communication (optional).

#### 2. **HTTP Request-Response Structure**
- **HTTP Request** consists of:
  1. Request Line (method, URI, HTTP version).
  2. Header fields.
  3. Blank line.
  4. Message body (optional).

  Example:
  - `GET /test.html HTTP/1.1`
  - `POST /index.html HTTP/1.1`
  
  <img src="12.png" alt="1" width="400px" height="250px">

- **HTTP Response** structure:
  1. Status line (HTTP version, status code, reason phrase).
  2. Response headers.
  3. Blank line.
  4. Response body (optional).

  Example status line:
  - `HTTP/1.1 200 OK`
  - `HTTP/1.0 404 Not Found`
  
  <img src="13.png" alt="1" width="400px" height="400px">

#### 3. **HTTP Methods (Verbs)**
- **GET**: Fetches a URL without changing the state of the server.
- **POST**: Submits data to the server and can change the server's state.
- **PUT**: Replaces a resource at a specified URL.
- **DELETE**: Deletes the specified resource.
- **HEAD**: Similar to GET but does not return the response body.
- **OPTIONS**: Describes communication options for the target resource.
- **PATCH**: Applies partial modifications to a resource.
- **TRACE**: Performs a message loop-back test.
- **CONNECT**: Establishes a tunnel to the server.
  
    ![14](14.png)

#### 4. **Common HTTP Status Codes**
- **1xx**: Informational.
- **2xx**: Success.
  - `200 OK`: Request succeeded.
  - `201 Created`: New resource created.
  - `204 No Content`: No response body.
- **3xx**: Redirection.
  - `301 Moved Permanently`: New URI assigned.
  - `302 Temporary Redirect`.
- **4xx**: Client Error.
  - `400 Bad Request`: Invalid request.
  - `401 Unauthorized`: Invalid credentials.
  - `403 Forbidden`: Access denied.
  - `404 Not Found`: Resource not found.
- **5xx**: Server Error.
  - `500 Internal Server Error`: Server encountered a problem.

#### 5. **HTTP Headers**
- **Request Headers**: Information about the client or request.
  - `Host`, `Connection`, `Accept`, `User-Agent`.
- **Response Headers**: Information about the server or the response.
  - `Content-Type`, `Content-Length`, `Keep-Alive`.

- **Caching Headers**:
  - **Cache-Control**: Specifies caching mechanisms.
    - `no-cache`, `no-store`, `public`, `private`.
  - **Expires**: Sets expiration time for cached responses.
  - **ETag**: Unique identifier for a specific version of a resource.
  - **Last-Modified**: Timestamp for the last modification of the resource.

#### 6. **Synchronous vs Asynchronous Communication**
- **Synchronous**: The client waits for the server to process and return the response.
- **Asynchronous**: The client continues with other tasks and processes the response later (used in modern web apps with AJAX, Fetch API, etc.).

#### 7. **Communication with Backend**
- **AJAX (Asynchronous JavaScript and XML)**: A method for sending and retrieving data asynchronously.
- **Fetch API**: Modern method for making HTTP requests in JavaScript, returning promises.
- **Webhooks**: Used to send real-time data from one application to another when an event occurs.
- **Polling**: The client repeatedly checks the server for updates at regular intervals.
- **Server-Sent Events**: Allows servers to push data to the browser.
- **WebSockets**: Enables full-duplex communication channels over a single, long-lived connection.

#### 8. **Bidirectional Communication**
- **WebSockets**: Provides a persistent connection between the client and server, allowing data to be sent in both directions.

#### 9. **Redirection**
- A **3xx status code** indicates a redirection, with the browser using the new URL provided in the `Location` header.
  - **Permanent Redirection**: `301 Moved Permanently`.
  - **Temporary Redirection**: `302 Temporary Redirect`.

#### 10. **HTTP Cookies**
- **Cookies**: Small pieces of data sent by the server to the client, stored by the browser, and sent back with future requests.
  - **Set-Cookie**: Header used to store a cookie on the client.
  - **Cookie**: Header used by the client to send stored cookies to the server.

#### 11. **Security Features**
- **HTTPS**: Secured version of HTTP using SSL/TLS encryption to protect data transmission between the client and server.

---

### Additional Notes:
- **AJAX and Fetch**: Key for modern web applications to provide a smooth user experience without page reloads.
- **WebSockets**: Particularly useful in real-time applications like chat apps or live notifications.
- **Statelessness in HTTP**: HTTP does not retain information between requests unless explicitly managed using cookies or tokens.

---

### Web Protocols (HTTP, HTTPS, HTTP/2, and QUIC)

---

#### **1. HTTP Connection Management**
- **Connection Header**: Controls whether the network connection stays open after the current transaction.
  - `Connection: keep-alive`: Keeps the connection persistent for future requests.
  - `Connection: close`: Closes the connection after the transaction.
  
- **Keep-Alive Header**: Sets a timeout and a maximum number of requests before closing the connection.
  - Example: `Keep-Alive: timeout=5, max=1000`

---

#### **2. HTTP/1.x**
- **Drawbacks of HTTP/1.x**:
  - Clients need multiple connections for concurrent requests.
  - **Head of Line Blocking**: Only one request is processed at a time.
  - No compression of request and response headers, causing network congestion.
  - Poor resource prioritization, leading to inefficient TCP usage.
  
  ![15](15.png)

---

#### **3. HTTP/2**
- **Improvements in HTTP/2**:
  - **Header Field Compression**: Reduces the size of headers using HPACK compression.
  - **Multiplexing**: Multiple concurrent exchanges over a single connection, reducing latency.
  - **Stream Prioritization**: Requests are prioritized, improving resource allocation.
  - **Binary Protocol**: HTTP/2 uses binary framing, improving message efficiency.

  <img src="16.png" alt="1" width="400px" height="250px">
  
- **Structure**:
  - **Frame**: Smallest unit of communication, which contains headers for stream identification.
  - **Message**: A sequence of frames representing a complete request or response.
  - **Stream**: A bidirectional flow of bytes within a single connection, carrying one or more messages.
  
- **Benefits**:
  - Fewer TCP connections improve network capacity.
  - **Server Push**: Server can push resources proactively into the client cache without waiting for requests.
  - Reduced round-trip time (RTT), leading to faster page loads.

  <img src="17.png" alt="1" width="500px" height="350px">
---

#### **4. QUIC (Quick UDP Internet Connections)**
- **Introduction**:
  - A new encrypted-by-default transport protocol designed to improve HTTP/2 performance.
  - Combines TCP and TLS handshakes into a single step.
  - **UDP-based**: It operates over User Datagram Protocol (UDP).
  
- **Benefits**:
  - Faster connection setup (only a single round trip needed).
  - Better congestion control and reduced **Head-of-Line blocking**.
  - Built-in security with encrypted connection metadata.
  
  <img src="18.png" alt="1" width="400px" height="250px">

---

#### **5. HTTP Versions**

  <img src="19.png" alt="1" width="400px" height="250px">

---

#### **6. HTTPS (HyperText Transfer Protocol Secure)**
- **Overview**:
  - HTTPS is the secure version of HTTP, used to encrypt communication between a client (browser) and a server.
  - **Port 443**: Default port for HTTPS.
  - Protects requests from being intercepted or modified by using encryption.

- **TLS Handshake**:
  - Establishes a secure connection between client and server.
  - Agrees on the protocol version and cryptographic algorithms.
  - Both parties authenticate each other via digital certificates.
  - **Symmetric Encryption**: Used for faster encryption once the handshake is complete.

  <img src="20.png" alt="1" width="400px" height="450px">
  <img src="21.png" alt="1" width="400px" height="350px">

---

#### **7. Digital Certificates and Certificate Authority (CA)**
- **Certificates**:
  - The server sends a public key certificate (SSL/TLS certificate) to the client to validate its identity.
  - A **Certificate Authority (CA)** issues these certificates, ensuring trust between the client and server.

---

### **Summary of Key Points**:
1. **HTTP Connection Management**: Keep-Alive for persistent connections.
2. **HTTP/1.x**: Limitations such as head-of-line blocking and inefficient resource use.
3. **HTTP/2**: Binary protocol with features like multiplexing and server push for better performance.
4. **QUIC**: A faster, more secure, UDP-based protocol with reduced handshake time and improved congestion control.
5. **HTTPS**: Encrypts data transmission using the TLS protocol, secured by digital certificates.

---
### Web Protocols (Module 3)

---

### **1. Introduction to Web Protocols**
- **Web Protocols** are essential for client-server communication on the internet.
- This module covers important web protocols such as HTTP, HTTP methods, headers, connection management, and communication between frontend and backend.

---

### **2. HTTP (HyperText Transfer Protocol)**
- **HTTP Request-Response Model**:
  - HTTP is a unidirectional protocol where the client (browser) initiates requests, and the server responds.
  - Request and response both have headers and body sections.
  
- **Request Structure**:
  - Method (GET, POST, etc.), URL, HTTP version.
  - Headers: Name-value pairs providing additional context (e.g., `Content-Type`, `Authorization`).
  - Body (optional): Data sent with the request (for POST, PUT).

- **Response Structure**:
  - Status line (HTTP version, status code, reason phrase).
  - Headers: Provide metadata about the response (e.g., `Content-Length`, `Content-Type`).
  - Body: The resource or data being returned.

---

### **3. HTTP Methods**
- **GET**: Retrieves data from the server.
- **POST**: Submits data to the server, often changing its state.
- **PUT**: Replaces all current data at the target URL.
- **DELETE**: Deletes the specified resource.
- **PATCH**: Partially modifies a resource.
- **OPTIONS**: Describes communication options for the resource.
  
---

### **4. Fetch API & Axios**
- **Fetch API**:
  - A modern interface for making HTTP requests from the client.
  - Uses the `fetch()` method, which returns a Promise.
  - Can be configured to handle different HTTP methods and headers.
  
- **Axios**:
  - A popular JavaScript library for making HTTP requests.
  - More user-friendly than Fetch, with built-in JSON parsing.
  - Can be used for both browser-based and Node.js HTTP requests.

**Key Differences**:
- Fetch API is built-in and doesn't require external dependencies.
- Axios needs to be installed but simplifies handling and transformations (e.g., JSON data).

![22](22.png)

---

### **5. Synchronous vs Asynchronous Communication**
- **Synchronous Communication**: The client waits for the server to finish processing before proceeding (e.g., typical form submissions).
- **Asynchronous Communication**: The client can continue executing other tasks while waiting for the server response (e.g., AJAX).

![23](23.png)

---

### **6. Long-Running Transactions**
- If a server task exceeds a typical request timeout, it often returns a **202 Accepted** response, indicating that the request is still being processed.
- Common techniques to handle long-running tasks:
  - **Polling**: The client checks the server at regular intervals for updates.
  - **Webhooks**: Server sends a notification to the client when the task is complete.
  - **Server-Sent Events (SSE)**: Server pushes updates to the client.
  - **WebSockets**: Full-duplex communication between client and server.

---

### **7. Communication Techniques**
- **HTTP Polling**:
  - The client makes repeated requests at set intervals, waiting for a server response.
  - Servers return either the requested resource or an empty response.
  - **Headers**: 
    - `Location`: The URL the client should poll.
    - `Retry-After`: Informs the client when to poll again.
  
  ![24](24.png)

- **Webhooks**:
  - Event-driven, HTTP-based callbacks.
  - The server sends data to the client only when an event occurs (no need for the client to poll).
  - Uses HTTP POST to send a payload to the client's webhook URL.

  ![25](25.png)

- **Server-Sent Events (SSE)**:
  - A unidirectional channel where the server sends real-time updates to the client.
  - The client connects using the **EventSource** API and listens for messages.
  - Common in live dashboards, notifications, or live feeds.

- **WebSockets**:
  - Provides bidirectional communication over a single TCP connection.
  - Allows real-time, full-duplex communication, ideal for chat applications, gaming, etc.
  - Uses a handshake protocol to upgrade from HTTP to WebSockets (via headers like `Upgrade` and `Sec-WebSocket-Key`).

  ![26](26.png)

---

### **8. Summary of Communication Methods**
- **Polling**: Client initiates repeated requests.
- **Webhooks**: Server initiates communication after an event.
- **SSE**: Server sends updates over a single HTTP connection.
- **WebSockets**: Real-time, bidirectional communication over a persistent connection.

---

### Client-Side and Server-Side in Web Communication

#### **Client-Side**
- **Definition**: The client-side refers to operations that are performed by the user’s device (browser, mobile app) when interacting with a server. 
- **Key Characteristics**:
  - The **client-side application** (e.g., frontend like React JS or AngularJS) sends requests to the server via HTTP protocols.
  - The **client-side** often cannot directly implement advanced techniques like Webhooks because they require a server to handle incoming HTTP POST requests.
  - **Pure frontend applications** (like React, Angular) cannot directly receive webhooks; instead, webhooks need a backend server to listen for events from the server.
  
- **Usage**:
  - Client-side applications make HTTP requests using **Fetch API** or **Axios** to retrieve data from the server or interact with APIs.
  - These client-side apps rely on server-side APIs to receive data asynchronously or synchronously.

#### **Server-Side**
- **Definition**: The server-side refers to operations carried out by the server in response to requests from the client. It includes handling business logic, database interactions, and providing resources back to the client.
  
- **Key Characteristics**:
  - The **server-side** runs server-based logic, processes requests, and sends responses to the client.
  - For communication like Webhooks, the server is responsible for receiving HTTP POST requests that are triggered by events from other systems.
  
- **Webhooks**:
  - In Webhooks, the **server-side** application sets up a URL (a webhook) that receives the POST request from another system when an event occurs.
  - When the event happens (e.g., a payment being completed), the event information is sent to the **server-side** webhook.
  
- **Full-Duplex Communication**:
  - **WebSockets**: The server and client engage in bidirectional communication over a persistent connection. 
  - The **server-side** handles real-time updates and pushes them to the client.

---

### **Use Cases**
- **Fetch API & Axios**: Ideal for making HTTP requests in client-server applications, such as fetching data or submitting forms.
- **Polling**: Useful when there is no other way for the client to be informed of a change.
- **Webhooks**: Best for applications needing notifications on specific events (e.g., payments, status changes).
- **SSE**: Great for live dashboards, news feeds, and live sports scores.
- **WebSockets**: Suited for real-time applications like chats, gaming, and live collaboration tools.

---

## REST (Representational State Transfer)

### 1. **Introduction to REST**
   - **Definition**: REST stands for Representational State Transfer. It is an **architectural style** for distributed hypermedia systems like the web.
   - **RESTful Web Services**: These expose information about resources (like docs, data, images, etc.) and allow the client to perform CRUD operations (Create, Read, Update, Delete) on them.

### 2. **Key REST Concepts**
   - **Resource**: Anything that can be uniquely identified and acted upon, such as a document, image, or data. Each resource has a unique identifier (URI).
   - **Representation**: The state of a resource returned to the client, usually in **JSON**, **XML**, or **HTML** formats.
   - **Example**: Fetching a specific Instagram user via their API will return details like name, post count, follower count, etc.

### 3. **Resources in REST**
   - **Main Building Blocks**: Resources and their representations (in formats like binary, JSON, XML).
   - **Identifiers**: Unique URIs used to retrieve specific resources.
   - **Metadata**: Information like content type and last modified time.
   - **Control Data**: Includes cache-control, is-modifiable-since headers, etc.

### 4. **REST and HTTP**
   - REST leverages **HTTP methods** to operate on resources:
     - **GET**: Retrieve a resource.
     - **POST**: Create a new resource.
     - **PUT**: Update an existing resource.
     - **PATCH**: Modify an existing resource.
     - **DELETE**: Remove a resource.
   - Other methods:
     - **HEAD**: Retrieve headers.
     - **OPTIONS**: Request allowed communication options for a URL.

### 5. **How REST Works**
   - **URL** (Uniform Resource Locator) identifies resources.
   - **HTTP Methods** define actions to perform on resources.
   - The client sends a request, and the server returns the state of the resource.

### 6. **HTTP Request Examples**
   - **GET Request**: Example of requesting `http://www.oreilly.com/index.html`, where the server returns the page with status code, headers, and content.

      ![27](27.png)

   - **SOAP vs REST**: 
     - SOAP: Uses XML-based messaging.
     - REST: Uses HTTP and is more lightweight and flexible.

      ![28](28.png)

   - **XML-RPC**: XML-based remote procedure call, an alternative to REST and SOAP.

      ![34](34.png)

### 7. **Scoping and Method Information**
   - **Scoping**: Identifying the specific resource or subset to operate on, often via URI path or query parameters.
   - **Method and Scoping**: RESTful services map the method to HTTP verbs and scoping to URIs.

### 8. **Key Principles of REST**
   - **Everything is a resource**: Every resource is uniquely identified via URIs.
   - **Use of standard HTTP methods**: Such as GET, POST, PUT, DELETE.
   - **Multiple representations**: Resources can have various representations like JSON, XML.
   - **Stateless communication**: Each request is independent, and the server does not retain any client information between requests.

### 9. **REST Constraints**
   To be RESTful, services must adhere to these six constraints:
   - **Client-Server Separation**: Server and client interact only via requests/responses, and are independent.
   - **Stateless**: The server does not remember the client’s state between requests.
   - **Cacheable**: Clients can cache responses for efficiency.
   - **Uniform Interface**: A consistent interface across the web with self-descriptive messages.
   - **Layered System**: Clients don’t need to know if intermediaries (e.g., caching, security) exist between them and the server.
   - **Code-on-Demand (Optional)**: Clients can request executable code from servers.

### 10. **Detailed REST Constraints**
   - **Client-Server Separation**:
     - The client initiates requests, and the server only responds to these requests.
   - **Stateless**:
     - The server does not store any session information; each request is self-contained.
     - Improves scalability and reliability.
   - **Cacheable**:
     - Responses include metadata (e.g., version numbers, expiration times) to inform clients whether the data can be cached.
     - Helps avoid redundant requests.
   - **Uniform Interface**:
     - Ensures that the API is simple and consistent.
     - Principles:
       1. **Identification of Resources**: Resources identified via URIs.
       2. **Manipulation of Resources**: Resources are manipulated via representations in requests.
       3. **Self-Descriptive Messages**: Each request and response contains enough information for both client and server to understand it.
       4. **HATEOAS (Hypermedia as the Engine of Application State)**: Hypermedia links in responses guide clients on how to proceed with further actions.

### 11. **HATEOAS**
   - **Hypermedia as the Engine of Application State**: Clients receive links to perform actions on resources in responses, allowing them to navigate the system dynamically.

      ![29](29.png)

### 12. **Layered System**
   - REST allows for intermediary layers (e.g., security, caching) between the client and server.
   - Clients are unaware of these layers, and these layers should not affect the response or request.

### 13. **Code on Demand (Optional)**
   - Though optional, the server can send executable code (like JavaScript) that the client can execute, adding additional flexibility.

### 14. **REST Maturity Model**
   - A model used to evaluate the maturity of a REST service based on:
     - **URI** usage.
     - **HTTP Methods**.
     - **HATEOAS** implementation.

      ![30](30.png)

### 15. **Conclusion**
   - REST is a stateless, cacheable, and scalable architecture that relies on standard HTTP methods and URIs to operate on resources.
   - Adherence to its constraints ensures flexibility, scalability, and simplicity, making it a popular choice for web services.

---

### Additional Information for Better Understanding:
1. **Idempotency**: 
   - In REST, certain operations (like GET, PUT, DELETE) are idempotent, meaning calling the same method multiple times results in the same state.
   - **POST** is not idempotent, as it may create multiple resources with repeated calls.

2. **REST vs SOAP**:
   - **REST** is lightweight, stateless, and uses JSON/XML. It is well-suited for web-based APIs.
   - **SOAP** is more rigid, requires XML, and is used in enterprise applications requiring strict contracts and advanced security.

3. **Content Negotiation**:
   - REST allows clients and servers to negotiate the format of the response (e.g., JSON, XML) through HTTP headers like `Accept`.

4. **Versioning**:
   - REST APIs often support versioning via URI paths (e.g., `/v1/users`), query parameters, or headers.

---

### **REST Design**

---

### **1. Agenda: Key Topics Covered**

- Interaction Design with HTTP (response codes, request methods)
- Identifier Design with URIs
- Metadata Design (Media Types, content negotiation)
- Representation Design (Message body format, Hypermedia Representation)

---

### **2. REST API Design**

REST API design is considered an art, with many practices implied by the HTTP standard. Key concerns in REST design:
- **Resource Naming**: Should URI path segments use singular or plural nouns?
- **Methods**: Which HTTP method should be used for different resource states?
- **Non-CRUD operations**: Mapping these to URIs.
- **Versioning**: Managing different versions of resources.
- **Hyperlinks in JSON**: How to structure these links.

### **3. API Design**

- **Resources**: Core elements around which REST APIs are designed.
  - A resource could be any object, data, or service accessible to the client.
- **Identifiers**: Each resource has a unique identifier (URI).
  - URIs should be based on **nouns** (resources), not **verbs** (actions on the resource).

#### **API Design Elements:**
- **Resource Representation**: How resources and their relations are represented.
- **HTTP Headers**: Standard and custom headers for requests and responses.
- **URI Structure**: Query interfaces for resource location and interaction.
- **Client Behaviors**: Handling retries, DNS caching, etc.

---

### **4. Interaction Design with HTTP**

REST APIs follow the **HyperText Transfer Protocol (HTTP)** model, embracing its request methods, response codes, and headers.

- **HTTP Methods**:
  - **GET**: Retrieve a resource's state.
  - **HEAD**: Retrieve metadata of a resource.
  - **PUT**: Add or update a resource.
  - **POST**: Create new resources or execute controllers.
  - **DELETE**: Remove a resource.

**Design Rules:**
- **GET**: Must be used to retrieve data, not to tunnel other methods.
- **POST**: Create resources or execute commands.
- **PUT**: Insert or update stored resources.
- **DELETE**: Remove resources.
- **OPTIONS**: Retrieve metadata on resource interactions.

#### **HTTP Response Codes:**
- **200 OK**: Generic success.
- **201 Created**: A new resource has been created.
- **204 No Content**: The response is empty but successful.
- **301 Moved Permanently**: Resource has a new permanent URI.
- **401 Unauthorized**: Authentication failure.
- **403 Forbidden**: Denied access.
- **404 Not Found**: Resource not found.
- **405 Method Not Allowed**: Invalid HTTP method for the request.
- **500 Internal Server Error**: Server-side error.

---

### **5. Identifier Design**

REST APIs rely on **Uniform Resource Identifiers (URIs)** to locate resources.

#### **URI Format**:
`URI = scheme "://" authority "/" path [ "?" query ] [ "#" fragment ]`

- Use forward slashes (/) to show hierarchical relationships between resources.
- Consistent subdomain names should be used across APIs.

#### **Resource Modeling**:
- **Paths** represent resources.
- Example URIs:
  - `/books/harry-potter`: Specific book.
  - `/books`: A collection of books.

#### **URI Design Rules**:
- **Singular Nouns** for documents.
- **Plural Nouns** for collections.
- **Verbs** for controllers.

    ![32](32.png)

#### **Antipatterns** to Avoid:
- Avoid CRUD function names in URIs (e.g., `/getUser` or `/deleteUser`).

  ![31](31.png)

#### **Filtering and Pagination**:
- Use query parameters to filter or paginate collections.
  - Example: `/orders?limit=25&offset=50`.

---

### **6. Metadata Design**

HTTP headers play a significant role in communication. Important headers include:
- **Content-Type**: Defines the media type of the resource (e.g., JSON, XML).
- **Content-Length**: Size of the response body.
- **Last-Modified**: Timestamp of the last modification.
- **E-tag**: Unique identifier for resource versions.
- **Location**: URI of newly created resources.

    ![33](33.png)

#### **Content Negotiation**:
When multiple representations of a resource are available, the API should support media type negotiation.

---

### **7. Representation Design**

The representation is the data format returned to the client. Common formats:
- **JSON** (preferred for REST APIs).
- **XML** or other formats as needed.

Representations should be:
- **Consistent**: Media types, links, and errors should follow a standard format.
- **Flexible**: To cater to varying application use cases.

**Example (JSON representation of a person)**:
```json
{
  "name": "John",
  "id": "urn:example:user:1234",
  "link": {
    "rel": "self",
    "href": "http://www.example.org/person/john"
  }
}
```

---

### **8. Best Practices**

- **Nouns over Verbs**: Use only nouns in URIs.
- **GET should be safe**: Must not alter resource state.
- **Plural nouns for collections**.
- **Use sub-resources** for resource relationships (e.g., `/books/1/authors`).
- **Use HTTP headers** for input/output formats.
- **Provide Pagination and Filtering** for large collections.
- **Versioning**: Include versioning in the API design.
- **Meaningful HTTP Status Codes**: Use proper response codes to convey the result of a request.

#### **Error Handling**:
Provide meaningful errors:
- Example: `invalid_auth` for revoked tokens.
- Example: `name_too_long` for invalid name inputs.

---

### **9. RESTful Services Example: Customer API**

| HTTP Verb | CRUD Operation | Entire Collection (`/customers`) | Specific Item (`/customers/{id}`) |
|-----------|----------------|----------------------------------|-----------------------------------|
| POST      | Create          | `201 Created`                   | `404 Not Found` or `409 Conflict` |
| GET       | Read            | `200 OK` (with pagination)       | `200 OK` or `404 Not Found`       |
| PUT       | Update/Replace  | `405 Method Not Allowed`         | `200 OK` or `204 No Content`      |
| PATCH     | Update/Modify   | `405 Method Not Allowed`         | `200 OK` or `204 No Content`      |
| DELETE    | Delete          | `405 Method Not Allowed`         | `200 OK` or `404 Not Found`       |

---

### **10. Summary**

- Focus on **simplicity** in API design.
- Use **consistent naming conventions** and **clear resource modeling**.
- Follow **HTTP standards** for methods, status codes, and headers.
- Provide **well-defined resource representations** for ease of use and flexibility.
- Ensure **meaningful error messages** to enhance client-side experience.

---