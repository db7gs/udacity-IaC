# Udacity-IaC
This is a project for udacity nanodegree Cloud dev-ops Engineer about infrastructure as a code.

### DESCRIPTION
This project deploys a VPC with two availabity zones with 1 public subnet and 1 private subnet on each availabity zone.
There is also one nat gatway on each public subnet.
There is a load balancer in front of the nat gatway.
Autoscaling group is considered for the private sub net with 2 EC2 on each availabilty zone.
To see the full components please open the udagram project 2 diagram.JPEG

**infraProject2.yml** file contains all the infrastructure needed to create a VPC, private and public subnets, Internet gateway, Nat Gateway,
Public route tables and private route tables and the Outputs of the project.

**NETWORK_TAMPLATE.yml** file is a template that contains all the infrastructure that you can deploy into Amazon AWS for future projects.

**Network-parameters.json** files contains all the parameters necessary for the infraproject2.yml file, with that we don't hard code into the
_infraProject2.yml_ file.

**udacityservers.yml** file contains all the servers configuration to run over the infrastruture like, Load balance, security groups, 
web server configuration, elastic load balancer, load balancer rules.

**udacityservers.json** file contains the environment name, with that we don't hard code into the _udacityservers.yml_ file.

### IMPORTANT

You should have AWS CLI Tool configurade in your pc.
For more information visit.  
(https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html)

### USAGE

create.sh is a sh file to run the infrastructure in AWS console, not necesary modification needed. 

To create the infrastructure run the following command in the console.
```
./create.sh [name of your stack] infraProject2.yml Network-parameters.json
```

to update the stack run the following command in the console.
```
./update.sh [name of your stack] infraProject2.yml Network-parameters.json
```

In order to create the Load balancer, security groups, launch configrations and app rules run the following command in the console
```
./create.sh [name of your stack] udacityservers.yml udacityservers.json
```

to update the stack frun the following command in the console.
```
./update.sh [name of your stack] udacityservers.yml udacityservers.json
```



License
-------
udacity-IaC is a public domain work, dedicated using
[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). Feel free to do
whatever you want with it.
