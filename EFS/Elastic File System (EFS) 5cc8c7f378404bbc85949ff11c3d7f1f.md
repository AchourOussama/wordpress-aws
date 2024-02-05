# Elastic File System (EFS)


# Instructions:

## Creating the EFS :

1. In the AWS Management Console:
    1. Type "ECS" in the search bar.
    2. Select "Clusters".
    3. Click "Create Cluster"
    
    ![Untitled](/EFS/efs-04.png)
    
    1. Filling the EFS basic information
    
    ![Untitled](/EFS/efs-05.png)
    
    1️⃣ giving a name for the EFS file system
    
    2️⃣ selecting the storage class:
    
    - standard : data is redundantly stored acdcross multile AZs
    - one zone : data is redundantly stored acdcross only one AZ
    
    💡For this project :we chose the *************standard class*************
    
    ![Untitled](/EFS/efs-06.png)
    
    💡As the arrows show, we define in which VPC the file system reside and the mount targets ;
    
    For the *mount targets* : 
    
    An EFS mount target is a network endpoint that allows resources to access an Amazon EFS file system. It acts as a gateway between the resource and the EFS file system, enabling file-level access.
    
    1️⃣ defining in which AZ the resource is located 
    
    2️⃣ defining in  which subvnet the resource is located
    
    3️⃣ the IP address is automatic since each new task will have its own IP address at the launch
    
    4️⃣ selecting the efs filesyetem security group  
    

## Creating a security group for the EFS:

[https://www.notion.so/Security-Groups-49d5fb10a966425fb62e92a034567624?pvs=4#51225dcaaf2f4d30a02e9186034aa39b](/Security%20Groups/Security%20Groups%2049d5fb10a966425fb62e92a034567624.md)