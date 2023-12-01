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
## Set up network security group for the three subnets
## set the inboun and outbound security rule




