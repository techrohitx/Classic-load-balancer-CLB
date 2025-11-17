# :anchor: **Classic Load Balancer A Mini Project**

## :round_pushpin:**Introduction**
This project demonstrates how to deploy an Classic Load Balancer(CLB) in linux. The Classic Load Balancer it
act like Round-Robin traffic distribution method. The classic load balancer is used in monolithic architecture
website. The main objective of this project was to learn how to deploy classic load balancer. Finally, The CLB
name of the classic load balancer is copied and tested to verify traffic disributtion.

## :o: **Steps for Implement**
**Step-1: Launch The Three Instance Server-1,Server-2,Server-3**
![Reference Image](/img/create3instance.png)

Add the following script in User Data while launching 3 Server instance:-

```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>This is classic Load Balencer $(hostname -f)</h1>" > /var/www/html/index.html
```
**Step-2: Create the classic load balancer & create button**
![Reference Image](/img/classicload.png)

**Step-3: Add The Available Instances.**
![Reference Image](/img/addinstance.png)

**Step-4: Add The Listeners and Routing.**
![Reference Image](/img/addlisteners%20rule.png)

**Step-5:Create Classic Loadbalancer Such as Classic-LB**
![Reference Image](/img/loadbalencer.png)

**Step-6: Copy the DNS name of the CLB.** 
![Reference Image](/img/dns.png)
  ## :globe_with_meridians:  **Expected Output Paste CLB DNS name in the new window.**
- **Server-1**
![Reference Image](/img/output-1.png)

- **Server-2**
![Reference Image](/img/output-2.png)

- **Server-3**
![Reference Image](/img/out-3.png)

## :red_circle: **Summary** 

The Classic Load Balancer (CLB) is one of AWS’s legacy load balancing services. It operates at both Layer 4
(TCP) and Layer 7 (HTTP/HTTPS), distributing incoming traffic across multiple EC2 instances to improve
application availability and reliability. CLB supports basic features such as SSL termination and sticky sessions,
making it suitable for small to medium-scale applications. However, for modern and advanced workloads,
AWS recommends using Application Load Balancer (ALB) or Network Load Balancer (NLB).
---

