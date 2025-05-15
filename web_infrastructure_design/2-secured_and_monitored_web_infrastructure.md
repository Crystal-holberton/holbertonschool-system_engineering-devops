# Web Infrastructure Explaination
## For every additional element, why you are adding it:
- 3 Firewalls: the first firewall checks the rules after receiving requests and could deny the request. The other firewalls are to prevent hacking and inspect the transaction of information.
- SSL certificate: added to secure https protocols and encrypt communication.
- 3 Monitoring clients: 2 are used to monitor each primary server and 1 to monitor the load-balancer. Helps to understand the performance of the resources according to users.

## What are firewalls for:
Firewalls are a network security device that monitors network traffic. They act as a barrier between the trusted internal networks and untrustable external networks to protect the infrastructure from cyber attacks.

## Why is the traffic served over HTTPS:
Hypertext Transfer Protocol Secure encrypts outgoing information and data transmitted between the user's browser and web servers.

## What monitoring is used for:
Monitoring tools are used to track the performance, availability and health of the infrastructure. They collect data by pulling information from servers, applicatons and network devices.

## How the monitoring tool is collecting data:
The foundation of the monitoring system are related to the lowest layer of the software stack, including physical and virtual devices. The software is the monitoring section that analyzes what is happening in these devices such as CPU usage, load, memory and running count. It then interprets the collected data using metric presented through graphs or data charts.

## Explain what to do if you want to monitor your web server QPS:
Queries per second is a measure of the rate of traffic going in a particular server serving a Web domain. To monitor the servers QPS the monitoring tool needs to be configured to collect metrics specific to the HTTP requests handled by the web server.

# Issues with this Infrastructure
## Why terminating SSL at the load balancer level is an issue:
This means traffic between the load-balancer and back-end servers are not encrypted which can expose sensitive data to potential interception.

## Why having only one MySQL server capable of accepting writes is an issue:
This creates a single point of failure. If the primary server goes down the application cannot process write requests. The single server may also struggle with high write loads.

## Why having servers with all the same components (database, web server and application server) might be a problem:
This setup lacks flexibility and scalability. If one component fails, the entire server goes down. Contention of resources causes components to compete for memory leading to performance degradation.