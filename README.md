# AWS_VPC

## CIDR block:
> - Classless inter-domain routing
> - These are blocks  which specify a range of to IP addresses in format of IPv4 Ipv6. Format of these blocks will be x.y.z.t/p. This essentially represents an 8 bit binary number. Hence why the range is up to 255. Combinations of these numbers becme an IPv4 IP address that must be unique to be able to idnetify a specific instance. 
> - In the case of AWS, p is a number from 16 to 28. This represents the number of bits that are inherited from given IP address. For example: 10.0.0.0/16 represents an IP address in following format: 10.0.x.y where x and y are any number from 0 to 255. So, actually it represents a range of IP addresses, starting from 10.0.0.0 to 10.0.255.255.
However for each CIDR block, AWS prohibits 5 possible IP addresses. Those are the first 4 available addresses and the last available address. In this case:

> - 10.0.0.0: Network address
> - 10.0.0.1: Reserved for VPC router
> - 10.0.0.2: DNS server
> - 10.0.0.3: Reserved for future use
> - 10.0.255.255: Network broadcast

## IPv4, IPv6 and Subnets
> - Internet Protocol version 4 is the fourth version of the Internet Protocol. It is one of the core protocols of standards-based internetworking methods in the Internet and other packet-switched networks.
> - Your VPC is associated with an IPv4 CIDR or both IPv4 and IPv6 CIDRs. If the subnet CIDRs you choose are IPv4 CIDR ranges, any EC2 instances launched within the subnet will communicate over IPv4-only.
> Internet Protocol version 6 is the most recent version of the Internet Protocol, the communications protocol that provides an identification and location system for computers on networks and routes traffic across the Internet.
> - Your VPC is associated with both IPv4 and IPv6 CIDRs. If you select the IPv6-only option when you create the subnet, any EC2 instances launched within the subnet will communicate over IPv6-only.
> - Dual-stack (IPv4 and IPv6): Your VPC is associated with an IPv4 CIDR or both IPv4 and IPv6 CIDRs. As a result, any subnets you create in the VPC can be dual-stack subnets. Any EC2 instances launched within the subnet will communicate over the IP of the subnet.

## Routing Table (RT)
> - In computer networking, a routing table, or routing information base, is a data table stored in a router or a network host that lists the routes to particular network destinations, and in some cases, metrics associated with those routes.

## Internet Gateways (IG)
> - An Internet gateway can transfer communications between an enterprise network and the Internet.

## NACLs 
> - An optional layer of security that acts as a firewall for controlling traffic in and out of a subnet. You can associate multiple subnets with a single network ACL, but a subnet can be associated with only one network ACL at a time.

## Difference between Stateless and Stateful
The key difference between stateful and stateless applications is that stateless applications don't “store” data whereas stateful applications require backing storage. Stateful applications like the Cassandra, MongoDB and mySQL databases all require some type of persistent storage that will survive service restarts.


# VPC CONGIF
> - Step 1 - Create a VPC
> - Step 2 - IG - Attach the IG with our VPC
> - Step 3 - Public subnet for our app 
> - Step 4 - Create RT with routes/rules - Edit routes to allow IG and VPC - Associate our RT to our public subnet
> - Step 5 - Create a security group now or create at when we launch our app - port 22 from my ip - port 3000 - port 80 HTTP - HTTPS - SSL
