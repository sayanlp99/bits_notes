### Scalable Services

---

### Introduction to Scalability

#### Definition
- **Scalability**: The capability of an architecture to handle increased workloads by scaling up (vertical) or scaling out (horizontal).

---

### Key Concepts: Performance, Consistency, and Availability

#### Performance
- **Definition**: The ability of a software system to meet timing requirements.

#### Availability
- **Definition**: The readiness of a software system to perform its tasks when needed.

#### Consistency
- **Definition**: Ensuring every read returns the most recent write.

---

### CAP Theorem

#### Explanation
- **CAP Theorem**: In a distributed system, you can only guarantee two of the following three: Consistency, Availability, and Partition Tolerance.
  - **Consistency**: Every read receives the most recent write.
  - **Availability**: Every request receives a response, regardless of success or failure.
  - **Partition Tolerance**: The system continues to function despite network partitions.
  ![1](1.png)

---

### Consistency Models

#### Eventual Consistency
- **Definition**: Ensures that the data store will eventually become consistent if no new updates are made.

#### Strong Consistency
- **Definition**: All nodes must contain the same data at any given time.

---

### System Availability

#### Key Resources for High Availability
- Multiple application servers
- Geographic distribution
- Backup systems

---

### Need for Scalable Architectures

#### Monolithic Architecture
- **Definition**: All modules of an application are interconnected in a single, self-contained unit.
- **Advantages**: Simplicity, low network latency, and enhanced security.
- **Disadvantages**: Scalability issues, slow development cycles, and long deployment times.

---

### Principles of Scalability

- Avoid single points of failure.
- Scale horizontally instead of vertically.
- Use APIs and caching mechanisms.
- Emphasize maintenance and automation.
- Implement asynchronous processing.

#### Focus Areas
- Availability
- Performance
- Reliability

---

### Guidelines for Building Highly Scalable Systems

- Avoid shared resources to prevent bottlenecks.
- Minimize reliance on slow services.
- Address the challenges of scaling the data tier.
- Utilize caching.
- Monitor system performance and health.

---

### Scalability Requirements

- Importance of early identification of scalability requirements.
- Criteria for system scalability:
  - Accommodating an increasing number of users.
  - Handling more transactions per millisecond.
  - Managing larger amounts of data.

---

### Challenges for Scalability

- Centralized approaches.
- Synchronous communication.
- Cost considerations.

---

### Case Study: YouTube

#### Architecture
- **Client/Server Architecture**: NetScaler implemented in front of web servers.
- **Web Servers**: Apache with mod_fastcgi, Python.

#### Video Streaming Challenges
- Bandwidth, hardware, and power consumption.
- Cluster methods to address consumption issues.
- Strategies for popular vs. less popular videos.

#### Database Management
- Initial use of MySQL.
- Shard architecture to solve replication problems.

---

### Managing and Processing High Volumes of Data

#### Partitioning and Sharding
- **Partitioning**: Dividing data into partitions for separate management and access.
  - **Benefits**:
    - Improved scalability
    - Enhanced performance
    - Increased security
    - Operational flexibility
    - Higher availability

#### Types of Partitioning
- **Horizontal Partitioning (Sharding)**: Dividing data rows across multiple database nodes.
- **Vertical Partitioning**: Dividing data columns across multiple database nodes.
- **Functional Partitioning**: Dividing data based on functionality or use case.
  
---

### NoSQL Databases

#### Document Model
- **Storage**: Stores and retrieves data as key-value pairs.
- **Structure**: Replaces traditional rows and columns with a document storage model.

#### Graph Model
- **Structure**: Entities as nodes and relationships as edges, each with a unique identifier.
- **Limitation**: Requires all data to reside on one machine, negating some NoSQL advantages.

#### Key-Value Model
- **Functionality**: Uses a key to retrieve and update data.

#### Column-Based Model
- **Structure**: Operates on columns based on Google's BigTable paper.
- **Storage**: Stores values of single columns contiguously.

---

### Hadoop Distributed File System (HDFS)

#### HDFS Components
- **Design**: Distributed file system designed for commodity hardware.
  ![2](2.png)
#### HDFS Write Process
- **Steps**:
  1. Application writes as to any file system.
  2. Client buffers until it gets a 64K block.
  3. Client informs NameNode of a new block write.
  4. NameNode returns a list of three DataNodes for the block.
  5. Client sends the block to the first DataNode and informs it of the other two replicas.
  6. First DataNode writes and sends the block to the second DataNode.
  7. Each DataNode reports completion to the client.
  8. Client commits the write to the NameNode after hearing from all DataNodes.

#### Failure Handling
- **Client Failure**: Application detects and retries.
- **NameNode Failure**: Backup NameNode takes over with a maintained log file.
- **DataNode Failure**: Client detects and requests a different DataNode.

#### Goals of HDFS
- Fast recovery from hardware failures
- Streaming data access
- Accommodation of large datasets
- Portability

---

### MapReduce Framework

#### How MapReduce Works
- **Map Function**: Processes input <key, value> pairs to produce intermediate pairs.
- **Reduce Function**: Processes intermediate <key, value> pairs to produce final output pairs.

#### Intermediate Steps
- **Combine**: Optional process to reduce data on each mapper server before passing downstream.
- **Partition**: Translates mapper output to feed the reducer and assigns it to a specific reducer.
![3](3.png)
---

### Content Delivery Network (CDN)

#### Concept
- **Definition**: A network of globally distributed computers that move data efficiently.
- **Example**: YouTube
  ![4](4.png)
---

### Case Studies

#### Video Streaming: Netflix
- **History**: Launched in 1998 as a DVD rental service, moved to streaming in 2007.
- **Architecture**: Streaming service architecture.
  ![5](5.png)

#### Web Conferencing: Zoom
- **Features**: Cloud-native, optimized for video, distributed architecture, multimedia routing, multi-bitrate encoding, application layer QoS.

#### Real-Time Fraud Detection
- **Process**: Uses Azure Event Hubs and Stream Analytics for detecting fraudulent transactions.

---

### Messaging Systems

#### Apache Kafka
- **Definition**: Publish-subscribe based durable messaging system.
- **Components**:
  - Kafka Topics
  - Partitioning
  - Kafka Brokers
  - Replication
  - Kafka Producers and Consumers
  - Kafka Connect and Streams
  ![6](6.png)
---

### Edge Computing

#### Concept
- **Definition**: Distributed IT architecture where client data is processed at the periphery of the network.
- **Benefits**:
  - Low latency
  - Longer battery life for IoT devices
  - Access to data analytics and AI
  - Resilience
  - Scalability
  - Efficient data management

#### Example
- **IoT Image and Audio Processing**: Processes data locally to extract key information like license plate numbers or people count in an area.

---
### Popular Scaling Approaches 

#### **1. Service Replicas**

- **Stateless Services**: 
  - These services do not maintain any state between requests. All instances of a stateless service are identical, and any request can be handled by any instance. 
  - **Example**: Web servers handling HTTP requests.

- **Stateful Services**: 
  - These services maintain state across multiple requests. Each instance might have a different state, so the request routing might depend on where the relevant state is maintained. 
  - **Example**: Database servers, shopping carts.

---

#### **2. Lifecycle of Stateful Replicas**

- **InBuild (IB)**: 
  - The replica is being prepared to join the replica set. Data is being copied to this replica, and it is getting ready to become operational.

- **Ready (RD)**: 
  - The replica is now part of the operational set and actively participates in the system's replication and quorum protocols.

- **Closing (CL)**: 
  - The replica is in the process of being shut down or removed from the replica set.

- **Dropped (DD)**: 
  - The replica has been fully decommissioned. It no longer exists, and its state has been completely removed from the system.

- **Down (D)**: 
  - The replica's service is not currently running, but the state is still preserved on disk.

- **Opening (OP)**: 
  - The replica is being brought back online after being down. It is transitioning back to an operational state.

- **StandBy (SB)**: 
  - The replica is not currently active but can be activated quickly if needed.

---

#### **3. Replica Roles**

- **Primary (P)**: 
  - This replica handles all the write operations. It is the authoritative source of data in the system.

- **ActiveSecondary (S)**: 
  - This replica receives updates from the primary and acknowledges them. It is a backup that can take over if the primary fails.

- **IdleSecondary (I)**: 
  - This is a secondary replica that is still being synchronized with the primary. It is not yet ready to take over.

- **None (N)**: 
  - The replica currently has no role in the replication process.

- **Unknown (U)**: 
  - The replica's role has not been determined yet. This is usually a temporary state during initialization.

---

#### **4. Load Balancing**

- **Concept**: 
  - Distributes incoming network or application traffic across multiple servers. Load balancing ensures that no single server becomes a bottleneck, improving overall application reliability and availability.
  
- **Types**:
  - **Hardware Load Balancers**: Physical devices dedicated to load balancing tasks.
  - **Software Load Balancers**: Software-based solutions often integrated into application delivery controllers (ADCs).

---

#### **5. Command Query Responsibility Segregation (CQRS)**

- **Overview**: 
  - CQRS is a pattern where the read and write operations are separated. It is beneficial in systems with high performance demands, allowing the read side and the write side to be scaled independently.
  
- **Benefits**:
  - Allows optimized data models for reading and writing.
  - Enhances security by segregating read and write access.
  - Improves performance by simplifying queries.

- **Challenges**:
  - Increases complexity due to the need for synchronization between read and write models.
  - Can introduce latency due to eventual consistency.
  ![7](7.png)

---

#### **6. Protocols for Communication**

- **Synchronous Communication**:
  - The client waits for the server to process the request and send a response before proceeding. Common in APIs where immediate feedback is needed.

- **Asynchronous Communication**:
  - The client sends a request and continues processing without waiting for a response. Useful in scenarios where responses are not time-sensitive, like messaging systems.
  ![8](8.png)

- **Sync vs Async communications vs Microservices**
    ![9](9.png)

---

#### **7. Message Broker**

- **Definition**: 
  - A system that manages communication between applications using messages. It supports asynchronous communication, which helps in decoupling applications.
  
- **Advantages**:
  - Reduces dependency between services.
  - Provides reliable message delivery.
  - Can buffer messages during high load, preventing system overload.

- **Disadvantages**:
  - Introduces complexity and potential points of failure.
  - May become a bottleneck if not scaled properly.

---

#### **8. Caching**

- **Purpose**: 
  - A technique to store frequently accessed data in a high-speed data storage layer (cache) to reduce access time and load on primary databases.

- **Distributed Cache**:
  - Spans multiple servers, ensuring that the cache can handle a large number of requests and provides fault tolerance. Common examples include Redis and Memcached.
  ![10](10.png)
---

#### **9. Scaling Techniques**

- **Vertical Scaling (Scaling Up)**: 
  - Increasing the capacity of a single machine (e.g., adding more CPU, RAM, or storage). It’s simple but has limitations as a single machine can only be scaled so far.

- **Horizontal Scaling (Scaling Out)**: 
  - Adding more machines to distribute the workload. It is more complex but provides greater scalability and fault tolerance.

- **Comparison**

  | **Vertical Vs Horizontal Scaling** | **Vertical Scaling**                        | **Horizontal Scaling**                            |
  |-----------------------------------|---------------------------------------------|--------------------------------------------------|
  | **Data**                          | Data is executed on a single node           | Data is partitioned and executed on multiple nodes |
  | **Data Management**               | Easy to manage – share data reference       | Complex task as there is no shared address space  |
  | **Downtime**                      | Downtime while upgrading the machine        | No downtime                                      |
  | **Upper limit**                   | Limited by machine specifications           | Not limited by machine specifications            |
  | **Cost**                          | Lower licensing fee                         | Higher licensing fee                             |

---

#### **10. Auto-Scaling**

- **Definition**:
  - Automatically adjusts the number of computing resources allocated to an application based on its current load. It helps maintain performance and reduce costs by scaling down during periods of low demand.

- **Benefits**:
  - Ensures applications remain performant during traffic spikes.
  - Reduces costs by scaling down during low usage periods.

---

#### **11. Cloud Scaling**

- **Benefits**:
  - **Speed**: Rapid deployment of additional resources.
  - **Flexibility**: Easy to scale services up or down.
  - **Cost Efficiency**: Pay only for the resources you use.
  - **Capacity**: Virtually unlimited resources available.

---

#### **12. Serverless Architecture**

- **Concept**:
  - Applications run in a stateless compute service where servers are abstracted away. Developers focus only on code, while the cloud provider manages the infrastructure.

- **Advantages**:
  - No need to manage servers, easy to scale.
  - Pay only for execution time, not idle time.

- **Limitations**:
  - May have performance overhead due to "cold starts".
  - Debugging and monitoring can be more challenging compared to traditional architectures.

---

#### **13. Virtualization**

- **Definition**: The creation of virtual (rather than physical) versions of something, such as servers, storage devices, or networks.
- **Benefits**:
  - **Resource Efficiency**: Multiple virtual machines (VMs) can run on a single physical machine, leading to better resource utilization.
  - **Isolation**: VMs are isolated from each other, providing security and fault tolerance.
  - **Flexibility**: Easy to create, modify, and move VMs across physical hosts.
  - **Scalability**: Allows for the rapid deployment of new instances without the need for additional hardware.
  
- **Types of Virtualization**:
  - **Hardware Virtualization**: Virtual machines emulate physical hardware.
  - **Network Virtualization**: Combines multiple network resources into a single, software-based administrative entity.
  - **Storage Virtualization**: Aggregates physical storage from multiple devices into a single storage pool.

- **Hypervisors**:
  - Software that creates and runs virtual machines.
  - **Type 1 (Bare Metal)**: Runs directly on the hardware (e.g., VMware ESXi, Microsoft Hyper-V).
  - **Type 2 (Hosted)**: Runs on a host operating system (e.g., VMware Workstation, Oracle VirtualBox).

---

#### **14. Load Balancer**

- **Definition**: A load balancer is a device or software that distributes incoming network traffic across multiple servers. It ensures that no single server becomes overwhelmed, thereby improving the availability and reliability of applications.

- **Types of Load Balancers**:
  - **Hardware Load Balancers**: Dedicated appliances that handle traffic distribution.
  - **Software Load Balancers**: Applications or services running on general-purpose hardware that distribute traffic (e.g., Nginx, HAProxy).

- **Load Balancing Algorithms**:
  - **Round Robin**: Distributes requests sequentially across servers.
  - **Least Connections**: Directs traffic to the server with the fewest active connections.
  - **IP Hash**: Routes requests based on the IP address of the client.
  - **Weighted Round Robin**: Similar to Round Robin but assigns more traffic to servers with higher capacity.

- **Key Features**:
  - **Health Checks**: Monitors server health to ensure traffic is only sent to healthy servers.
  - **SSL Termination**: Decrypts SSL/TLS traffic before passing it to servers.
  - **Session Persistence**: Ensures that a client is always directed to the same server for the duration of a session (also known as "sticky sessions").
  
- **Benefits**:
  - **Improved Performance**: By distributing the workload, applications can handle more requests efficiently.
  - **High Availability**: If one server fails, traffic is automatically redirected to other available servers.
  - **Scalability**: Simplifies the process of adding or removing servers based on demand.

- **Challenges**:
  - **Complexity**: Requires proper configuration and maintenance.
  - **Single Point of Failure**: If not designed with redundancy, the load balancer itself can become a bottleneck or failure point. 
  ![11](11.png)