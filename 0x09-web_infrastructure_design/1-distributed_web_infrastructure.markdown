# 1-distributed_web_infrastructure

## Diagram
![Distributed Web Stack](https://flic.kr/p/2rdeFNx)

## Infrastructure Specifics

### Additional Elements and Purpose
- **Load Balancer**: Distributes incoming traffic across multiple servers. Added to improve scalability, reduce single point of failure (SPOF), and handle high traffic.
- **Second Server**: Hosts duplicate Nginx, application server, and application files. Added to enable redundancy and load distribution.
- **Database Primary-Replica Cluster**: Primary MySQL node handles writes; Replica node handles reads. Added to enhance database availability and performance.

### Explanations
- **Load Balancer Algorithm**: Configured with **Round-Robin**. It distributes requests sequentially to each server in a circular order, ensuring even load distribution across servers.
- **Active-Active vs. Active-Passive**:
  - **Active-Active**: Both servers handle traffic simultaneously, improving performance. Our load balancer uses this setup for maximum resource utilization.
  - **Active-Passive**: One server is active, while the other is on standby, only activating if the primary fails. Active-Active is preferred here for scalability.
- **Database Primary-Replica Cluster**: The Primary node accepts write and read queries, replicating data to the Replica node, which handles read-only queries to reduce load on the Primary.
- **Primary vs. Replica Node**:
  - **Primary Node**: Handles all write operations (e.g., INSERT, UPDATE) and read queries from the application, ensuring data consistency.
  - **Replica Node**: Handles read-only queries, offloading read traffic from the Primary to improve performance and scalability.