# Implementing-multi-tier-web-in-Azure
# Use Draw i.o to define the network architecture for web, application and database.
![diagram](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/52739c59-16b6-409e-99e0-1adf8c2ccc4d)
## Open Powershell on the local system
## Log into azure account with "az login"
# Create a resource group with "az group create --resource-group with location in east us
## Create resource group with "az group create --resource-group webtierRG --location eastus"
![resource group](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/9b393715-7919-4786-a5b1-788bf1c9b8a7)
# Create an azure virtual network with a front end subnet as follows;
## az network vnet creat --resource-group --webtierRG --name webvnet --address-prefix 10.1.0.0/16 --subnet-name webnet --subnet-prefix 10.1.2.0/24
![create vnets](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/13c68e65-3492-4409-b7d7-c1bb7bd2565d)
# Create a backend subnet called appsubnet:
## az network vnet subnet create --resource-group WebtierRG --vnet-name --webvnet webnet --name appsubnet --address-prefix 10.1.2.0/24
![creating subnets](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/8850b64d-1dc6-4ddb-83dd-239d5d3e7f69)
# Create an application vnet called datanet:
## Create datanet using "az network vnet subnet create --resource-group WebtierRG --vnet-name Webvnet --name datanet --address-prefix 10.1.3.0/24
![create subnets](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/1c591e32-7617-4321-a8b9-cecbd230b7ad)
# Open the azure portal to create the Network Security group (NSG)
## Deploy virtual machines into the respective subnets
### put in the same resource group created and name the machines
### Locate the machines in East US
### Deploy the machines into the respective sub nets
## Set up network security group for the three subnets
## set the inbound and outbound security rule
![nsg inbound and outbound rules](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/3a87cee7-4bc2-4986-805e-02138d03a762)
![nsg inbound rules](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/09514427-ef2f-4c4b-9d1d-830f8c90809f)
![outbound rule](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/0d6e1aed-f22f-46e4-af06-21734cd05f5c)
# Create public-facing Load Balancer for each subnets 
## search for load Balancer in the portal and create
## set it so as to evenly distribute loads between the servers in order to improve application performance
![resources](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/c015f5b8-50e1-4913-ae9c-d5496dd7d0ba)
![deployments;NSG,load balancer](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/62374871-3c44-418d-9ef4-0e8f80fcbe18)
![visualizer](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/0bcf88f7-10a6-4d1f-ab4b-017ee45f3b39)
![deployments](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/b9f13e23-5276-4698-b7ce-c9dcd89c20fa)












