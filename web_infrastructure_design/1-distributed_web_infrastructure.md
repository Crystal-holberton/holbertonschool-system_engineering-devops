# Infrastructure Explaination
## For every additional element, why you are adding it:
The Load-Balancer (HAproxy) distributes incoming traffic evenly between the two web servers to reduce individual servers from becoming overwelmed. The two servers take exactly the same setup so if one server fails the other can continue with traffic. Finally there is a centralized storage for application data allowing both servers to access and manipulate data.

## What distribution algorithm your load balancer is configured with and how it works:
The load-balancer is using a Round Robin algorithm distribution. Requests are distributed sequentially across available servers.

## Is your load-balancer enabling an Active-Active or Active-Passive setup, explain the difference between both:
The loader-balancer is enabling an Active-Active setup. 

### Active-active:
- all servers in cluster are actively handling traffic
- workload is distributed across all active servers
- handles higher traffic volumes
- high availability
- if a server fails traffic is redirected to the other servers
- more complex to configure and manage

### Active-passive:
- one server handles all traffic and other servers standby
- primary server handles full workload
- if primary server fails the secondary server takes over
- simple to configure and manage
- more cost affective
- may experience downtime

## How a database Primary-Replica cluster works:
The primary node handles all inserts, updates and deletes and serves as the main source of data. It is the authoritative source for the database. The replica copies the data from the primary node and handles the queries. The primary node periodically sends updates to the replica nodes. The replicas then apply these updates to their data stores to stay synced along with the primary.

## What is the difference between the Primary node and the Replica node in regard to the application:
The main difference between the primary node and the replica node is the primary database is the authorative source that serves as the keeper of real data and only writing happens. The replica database synchronizes to the primary and is normally reading only. However, the replica node can take on writing and reading requests to prevent the primary from overloading during heavy traffic.

# Issues with this infrastructure
## Where are SPOF:
If the database (MySQL) fails the entire application loses access to the data. If the load-balancer (HAproxy) fails the incoming traffic cannot be distributed.

## Security issues (no firewall, no HTTPS):
Without a firewall, the infrastructure is exposed to potential attacks from a variety of different external sources. Not using HTTPS means data transmitted between users and the web servers is not encrypted which makes it vulnerable to interception and tampering.

## No monitoring:
There is a lack of visibility to track server performance, detect failures, or identify potential issues before they affect users.