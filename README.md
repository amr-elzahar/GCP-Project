# ITI GCP Final Project

This project is all about to deploy a simple python application on a GKE cluster. The infrastructure is fully created with Terraform

## Installation

Use the Terraform commands to create the infrastructure

```bash

#To authenticate (you may use this link https://registry.terraform.io/providers/hashicorp/google/latest/docs/guides/getting_started):
cloud auth application-default login
  
#To initialize working directory containing configuration files 
terraform init

#To format your code
terraform fmt

#To create the infrastructure 
terraform apply --auto-approve
```

## Usage
NOTE: before you start, you have to push the application docker image to google container registry.
  
Steps:
1) SSH to the VM instance

![SSH To VM](https://github.com/amr-elzahar/GCP-Project/blob/main/images/ssh-to-vm.png?raw=true)

2) Connect to GKE cluster using command line access provided by google (you get this command from the connect button in cluster details page or from cluster actions and then choose connect)

![SSH To VM](https://github.com/amr-elzahar/GCP-Project/blob/main/images/gke-details.png?raw=true)

![SSH To VM](https://github.com/amr-elzahar/GCP-Project/blob/main/images/connect-command.png?raw=true)

################################ OR ################################

![SSH To VM](https://github.com/amr-elzahar/GCP-Project/blob/main/images/actions-connect.png?raw=true)

![SSH To VM](https://github.com/amr-elzahar/GCP-Project/blob/main/images/connect-command.png?raw=true)

Successfully connected:

![SSH To VM](https://github.com/amr-elzahar/GCP-Project/blob/main/images/connect-to-gke-cluster.png?raw=true)


3) After the connection is established, you could create a deployment and a service using kubernetes files  
```bash
kubectl create -f .
```
![SSH To VM](https://github.com/amr-elzahar/GCP-Project/blob/main/images/all-objects-running.png?raw=true)


4) From loadbalancer console management page, you can use loadbalancer ip:port to access the application

![SSH To VM](https://github.com/amr-elzahar/GCP-Project/blob/main/images/loadbalancer-ip.png?raw=true)

5) The final output is gonna be something like that:

![SSH To VM](https://github.com/amr-elzahar/GCP-Project/blob/main/images/final-output.png?raw=true)
