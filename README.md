# Jenkins Distributed Architecture Setup

## Provision VM

- Provision 2 Ec2 instance on AWS. One instance will be used for Java Agent and another for ssh connection
- While luanching instance ensure to define key



## Configuring Jenkins
- Navigate to ManageJenkins--> Security--> Agent
- Enable TCP port for inbound agents
- Select Fixed, and give port value as 50000

## Adding Node as Java Agent
- Naivate to ManageJenkins--> Node
- Choose Type as Permanent Agent and click Create
- Follow instruction and Save 
- - Define label of your choice like ssh
- - Remote Dir as /home/ubuntu
- - Lanuch Method - Connecting by controller
- On Node page, click on Agent name, it will display some commands. We will need to run these command on Agent terminal

 ### Connecting Slave with Master
  - Update package 
  - Install Java
  - Run command displayed on master node page
  - keep the process running, so not terminate process

## Adding Node using SSH
- Naivate to ManageJenkins--> Node
- Choose Type as Permanent Agent and click Create
- Follow instruction and Save 
- - Define label of your choice like ssh
- - Remote Dir as /home/ubuntu
- - Lanuch Method - via ssh
- - Add host and credentials, private key for slave node
- - Select 'Non verifying' in Host key verification
- On Node page, check the status, you can relauch and check logs