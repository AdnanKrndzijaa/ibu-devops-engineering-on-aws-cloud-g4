# ibu-devops-engineering-on-aws-cloud-group-4

## Team members
1. [Amina Kodžaga](https://github.com/aminakodzaga)
2. [Adnan Krndžija](https://github.com/AdnanKrndzijaa)
3. [Adnan Brkić](https://github.com/kojiado)

## Repository description
- There are two folders on the GitHub repository (resources and docs). The application code is in the resources folder, and all the documentation required for the project is in the docs folder.
- The documentation includes a README.md file in which everything we did on the project is explained, an estimate of costs on a monthly and annual level, including the necessary services in AWS, and an architectural diagram of the project.

## Project description (University Website)
### Phase 1
- In first phase, we created a diagram and estimated costs for AWS services on a monthly and annual basis. On the diagram you can see how we planned our project to look like, and in the end we did everything that way. 
- We divided the system into two availability zones (us-east-1a & us-east-1b) and did a part of the work in each one, so that in the end we could combine it all and get a project that as a whole is fully functional.

SLIKA DIAGRAM I COST
![image](https://github.com/AdnanKrndzijaa/ibu-devops-engineering-on-aws-cloud-group-4/assets/92021913/4c50fbd4-a856-4dc6-8441-63985a1c27cd)


### Phase 2
- In the second phase, we created VPC, 2 public and 2 private subnets, internet gateway, NAT gateway and security groups, after which we connected all these things to be properly workable. 
- We used a script with code from the AWS Academy course and used it when creating a new instance (Group4 PublicInstance). This instance was created for the website together with the database, so it was necessary to use a Session Manager to successfully bring everything together and work.
- We have successfully created a virtual machine using EC2 Instance, using Ubuntu Amazon Machine Image.
- Then we tested the CRUD operations on our website and found that everything works correctly (adding, deleting, updating and listing data).

NEKE SLIKE

### Phase 3
- Given that we already created the necessary 2 private subnets in the previous phase (each for one availability zone), we moved on to creating a new instance (Phase3Instance) for which we used a new script without a predefined database, and using the LabInstanceProfile IAM role. 
- After that, we created an Amazon RDS database for MySQL, which will later be connected to a new instance. 
- Immediately after that, we created Cloud9 and ran the script to create a secret on the Secrets Manager. Inside the Secrets Manager service there was a secret that we created and it contained all the data about the database, including the user, db name, host endpoint and db password.
- When we checked that everything was created as we set it up, we moved on to migrating the old database to the new one and connecting the new instance to that created database, within the Amazon RDS service. Using the commands from the script, we managed to migrate the data from the first original database to the newly created one and thus successfully merge and complete this phase of the project. After a successful connection, we were able to successfully read "old" data, edit, and  delete them, but also to add new data on the new instance.

![image](https://github.com/AdnanKrndzijaa/ibu-devops-engineering-on-aws-cloud-group-4/assets/92021913/de9df513-2415-4b76-ada5-0f63f8ef6a03)

### Phase 4
- In the last phase, we implemented high availability and scalability, services that will improve our website. 
- First we created the AMI Image for the instance we created in Phase 3. Then we created the Load Balancer and Auto Scaling group. For ASG, we primarily needed a Launch Template, which we also had to create. We checked the created services and confirmed that they were successfully created as we specified them, and then using the DNS name from ELB, we accessed our website and tested it. Our website was now fully created, with all the plugins we created and set up afterwards.
- As the last task within this phase, we performed load testing of this application with the help of commands from the script. We started the Load testing installation command within the Cloud9 service, and then the testing command.

![image](https://github.com/AdnanKrndzijaa/ibu-devops-engineering-on-aws-cloud-group-4/assets/92021913/36d898df-aad4-4d7d-afd4-5897ef5897f9)
