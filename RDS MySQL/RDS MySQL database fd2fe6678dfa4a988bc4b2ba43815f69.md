# RDS MySQL database


# Instructions:

## Creating the RDS MySQL database:

1. In the AWS Management Console:
    1. Type "ECS" in the search bar.
    2. Select "Clusters".
    3. Click "Create Cluster".
    
    ![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/db-15.png](/RDS%20MySQL/RDS%20MySQL%20creation/db-15.png)
    
2. Specifying basic information about the type and creation method of the database
    - Specifying the creation method
        
        💡For this project: we chose the *standard method* since it gives us much more flexibility in customizing the configuration of the database rather than the easy create.
        
    
    ![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/db-14.png](/RDS%20MySQL/RDS%20MySQL%20creation/db-14.png)
    
    - Specifying the engine type
        
        💡For this project: we chose the MySQL engine type (since it is included in the AWS free tier plan).
        
    
    ![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/db-13.png](/RDS%20MySQL/RDS%20MySQL%20creation/db-13.png)
    
    - Specifying the engine version
    
    ![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/db-12.png](/RDS%20MySQL/RDS%20MySQL%20creation/db-12.png)
    
    - Specifying a template to meet our use case of the database
    
    💡For this project: we chose the free tier since it both satisfies our needs and doesn’t charge us big fees.
    
    ![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/db-11.png](/RDS%20MySQL/RDS%20MySQL%20creation/db-11.png)
    
    1. Filling the database settings
        1. Naming the DB cluster
    
    ![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/Untitled.png](/RDS%20MySQL/RDS%20MySQL%20creation/Untitled.png)
    
    ```
    b. Defining the credentials settings
    
    ```
    
    - The database admin username
    - The admin’s password
    
    ![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/db-10.png](/RDS%20MySQL/RDS%20MySQL%20creation/db-10.png)
    
    1. Specifying the instance configuration
    
    ![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/Untitled%201.png](/RDS%20MySQL/RDS%20MySQL%20creation/Untitled1.png)
    
    💡For this project: since we are choosing the free tier plan, we will have access only to the t classes instances. That being said, these instance classes satisfy our needs for this project.
    
    1. Specifying the storage type and size
    
    ![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/Untitled%202.png](/RDS%20MySQL/RDS%20MySQL%20creation/Untitled2.png)
    
    1. Configuring the connectivity
    
    ![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/Untitled%203.png](/RDS%20MySQL/RDS%20MySQL%20creation/Untitled3.png)
    
    1️⃣ Selecting where the database instance will reside
    
    2️⃣ Selecting the subnet group of the subnet (this subnet has been created just to contain the database instance)
    
    ![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/Untitled%204.png](/RDS%20MySQL/RDS%20MySQL%20creation/db-04.png)
    
    1️⃣ Making the database not directly accessible via the internet
    
    💡For this project: the database only communicates with the WordPress tasks.
    
    2️⃣ Selecting a security group for the database
    
    1. Additional configuration:
        
        Defining a database name which will be one of the environment variables of the WordPress tasks (in order to establish a connection with the database)
        
    
    ![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/Untitled%205.png](/RDS%20MySQL/RDS%20MySQL%20creation/db-03.png)
    

## Checking the database information:

- As we see, our database is available

![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/Untitled%206.png](/RDS%20MySQL/RDS%20MySQL%20creation/db-02.png)

- Useful information about the database

![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/Untitled%207.png](/RDS%20MySQL/RDS%20MySQL%20creation/db-00.png)

1️⃣ Database instance name

2️⃣ Database master username

- Useful information about the database connectivity and security

![RDS%20MySQL%20database%20fd2fe6678dfa4a988bc4b2ba43815f69/Untitled%208.png](/RDS%20MySQL/RDS%20MySQL%20creation/db-01.png)

1️⃣ The database endpoint

2️⃣ The actual location of the database instance

3️⃣ Subnets of the resources that could access the database

4️⃣ The database security group

## Creating a security group for the RDS MySQL database:

[https://www.notion.so/Security-Groups-49d5fb10a966425fb62e92a034567624?pvs=4#f4fc76e752b145b18261e6ad39067862](/Security%20Groups/Security%20Groups%2049d5fb10a966425fb62e92a034567624.md)