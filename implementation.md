# implementation

# Overview :

This a step-by-step documentation that covers all the technical implementation of the architecture that we have desinged for the wordpress wesbite project 

---

# Architedute diagram:

![wordpress website .png](./Images/wordpress%20website%20.png)

⚠️Please refer to the project report in case you would like to know about any component or detail of the architecutre 

# Stages :

### Setting up the VPC  :

[VPC](VPC\VPC 9048cce4791b4ba9a0cb45612060b464.md)

### Creating security groups for the resources included in this architecture :

[Security Groups](Security Groups\Security Groups 49d5fb10a966425fb62e92a034567624.md)

### Creating/provisioning the different services/resources

- Elastic Container Registry (ECS) cluster :
    
    [Elastic Container Service (ECS)](ECS\Elastic Container Service (ECS) 8a850e733f9b4cf6b0f50743ab1fb7fc.md)
    
- Relational Database Service (RDS) MySQL database:
    
    [RDS MySQL database](RDS MySQL\RDS MySQL database fd2fe6678dfa4a988bc4b2ba43815f69.md)
    
- Elastic File System (EFS) filesystem
    
    [Elastic File System (EFS)](EFS\Elastic File System (EFS) 5cc8c7f378404bbc85949ff11c3d7f1f.md)
    
- Application Load Balancer
    
    [Application Load Balancer (ALB)](ALB\Application Load Balancer (ALB) 32ab4bc97415421a95d2a36a3acee1f7.md)
    

### Installing the WordPress instance :

[wordpress installation ](WordPress installation\wordpress installation 2dedc8ab83cf414794afb5de898bed26.md)

### Running a service using the load balancer:

[Running a service](Creating a service\Running a service de4adc0450cb4cda9a6fa7fc8ff97fc2.md)