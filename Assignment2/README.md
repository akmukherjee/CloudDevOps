# Deploy a highly available web application using CloudFormation

#### There are two sets of files, the YAML files and the JSON files. The YAML files create the environment as shown below and the JSON file serve as input parameters to the environment.
 		
#### The **network.yaml** file is for creating the network VPC, Subnets etc. using the **network.json** as input parameters. The **bastion.yaml** creates a Bastion Host to remote into the Web Servers using **bastion-params.json** as the input. The webservers which include the Load Balancer, AutoScaling Groups and Security Groups are created using **udacity-servers.yaml** using the **server-params.json** file as the input. There is also a **single-server.yaml** file which creates a single server for some troubleshooting and debugging if needed. There are also a couple of batch files which ease the creation and updating of the stacks. Please ensure that you have a pre-created Key Pair for the Bastion Host. Ensure that you use the **same** environment variable for all the stacks. 


## Instructions

#### First create the network by running the create.bat file as below:

```
create Udacity-Network network.yaml network.json
```

#### Then create the bastion host by running the create.bat file again.Make sure to update the bastion-params file with your own Key Pair name.

```
create BastionStack bastion.yaml bastion-params.json
```
#### Finally Create the Web Stack by running the create file as shown below.


```
create WebserverStack bastion.yaml bastion-params.json
```
