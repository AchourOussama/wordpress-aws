# Application Load Balancer (ALB)

# Overview:

---

# Instructions:

## Creating the ALB:

1. In the AWS Management Console, we:
    1. Type "ALB" in the search bar.
    2. Select "Load Balancers".
    3. Click "Create Load Balancer".

![Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-03.png](Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-03.png)

1. At this level, AWS gives us a description and comparison of the different types of load balancers we can create.
    
    💡 For this project, we chose the "Application Load Balancer".
    
    As it shows, this type of load balancer is responsible for distributing HTTP/HTTPS traffic.
    

![Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-04.png](Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-04.png)

Here is a brief description of how an Elastic Load Balancer (ELB) works:

![Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-05.png](Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-05.png)

1. Filling the ALB basic configuration information.

![Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-06.png](Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-06.png)

1️⃣ Giving a name for the load balancer.

2️⃣ Defining the scheme of the load balancer.

In fact, the "scheme" tells us whether the load balancer is an internal load balancer (The nodes of an internet-facing load balancer have public IP addresses, thus it requires a public subnet) or an internet-facing load balancer (The nodes of an internal load balancer have only private IP addresses).

💡 For this project, we chose the "internet-facing scheme".

3️⃣ Selecting the IP address type.

In fact, the Application Load Balancer supports both IPv4 and IPv6.

💡 For this project, we chose the "IPv4 address type".

1. Defining the VPC where the ALB resides.

![Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-07.png](Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-07.png)

1. Defining the Network Mapping information.

![Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-08.png](Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-08.png)

First, we select which Availability Zones to which the ALB will distribute the traffic.

Second, we select which subnet in each AZ.

⚠️ In our case, the subnet should be public since we chose for the ALB to be an internet-facing.

💡 For this project, each arrow shows what AZ we selected as well as the public subnet for each AZ.

1. Selecting a security group for the ALB.

⚠️ Please refer to the [ [https://www.notion.so/Security-Groups-49d5fb10a966425fb62e92a034567624?pvs=4#89589e917a4d4c3fafb77e2d8406f6ae](Security%20Groups%2049d5fb10a966425fb62e92a034567624.md)  ]to see how we created a security group for this ALB.

![Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-09.png](Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-09.png)

1. Defining the "listeners" and the "target groups".

![Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-10.png](Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/ALB-10.png)

1️⃣ & 2️⃣ Selecting what types of traffic the ALB's listener will listen to.

💡 For this project, we chose "HTTP" traffic.

3️⃣ Defining the default action to take once receiving that type of traffic.

Usually, the action is to forward the traffic to the target group (a target group is a logical group that we define to route incoming traffic from the load balancer to the registered targets; in our case, ECS tasks).

💡 For this project, we selected the target group that we created (it seems as we didn't select a target group, however, the AWS console has prevented us from reselecting the created target group since we already selected it when creating the real ALB).

## Creating the target group:

1. In the AWS Management Console:
    1. Type "target groups" in the search bar.
    2. Click "Create Target Group".

![Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/target_group-00.png](Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/target_group-00.png)

1. Specifying the target type:

![Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/target_group-01.png](Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/target_group-01.png)

The "target type" refers to the type of resources that will be registered as targets in the group.

💡 For this project, we are using Fargate as a serverless compute engine, thus we don't have access to the underlying EC2 instances hosting our tasks. Therefore, we can't specify our targets via an instance. Instead, each task will have an IP address.

1. Filling the target group configuration information:

![Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/target_group-02.png](Application%20Load%20Balancer%20(ALB)%2032ab4bc97415421a95d2a36a3acee1f7/target_group-02.png)

1️⃣ Giving a name for the target group.

2️⃣ Specifying which traffic type (protocol & port).

3️⃣ Specifying in which VPC we want to include this target group.

4️⃣ Specifying the protocol version.