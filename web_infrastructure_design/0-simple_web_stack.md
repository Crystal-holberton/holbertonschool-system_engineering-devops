# Web Infrastructure Explaination
## What is a server:
Servers can be physical machines, virtual machines or softwares that provide functionality to programs or devices called “clients”. It runs server software that listens for requests from clients and responds with the appropriate data or services.

## What is the role of the domain name:
The domain name replaces complex IP address numbers into easily understandable names (such as foobar.com) that users can remember.

## What type of DNS record www is in www.foobar.com:
The DNS record of www belongs to a subdomain of the www.foobar.com which points directly to the IP address of the server hosting the site (8.8.8.8).

## What is the role of the web server:
The web server (Nginx) stores the files of a site and broadcasts them over the internet so they can be visited by users. 

## What is the role of the application server:
The intermediary between dynamic content from applications and back-end databases therefore generating a response from the web server to send back to the client.

## What is the role of the database:
The database (MySQL) is to make the information gathered organised so it is easily accessed, managed and updated.

## What is the server using to communicate with the computer of the user requesting the website:
The server is using Hypertext Transfer Protocol (HTTP). This enables transfer of resources and data between the users web browser and the server.

# Issues with this Infrastructure
## SPOF:
Single Point of Failure is where if a component of the system fails, there is no backup that can support the continued functionality of the system.

## Downtime when maintenance needed:
If repairs are needed, the whole system has to be shutdown to complete them.

## Cannot scale if too much incoming traffic:
Risk to server capacity because there is no possibility to scale the service with additional backup servers.