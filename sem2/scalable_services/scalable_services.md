### Scalable Services: Course Overview

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

---

### Content Delivery Network (CDN)

#### Concept
- **Definition**: A network of globally distributed computers that move data efficiently.
- **Example**: YouTube

---

### Case Studies

#### Video Streaming: Netflix
- **History**: Launched in 1998 as a DVD rental service, moved to streaming in 2007.
- **Architecture**: Streaming service architecture.

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
