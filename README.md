# Implementing-multi-tier-web-in-Azure
# Use Draw i.o to define the network architecture for web, application and database.
![diagram](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/52739c59-16b6-409e-99e0-1adf8c2ccc4d)
## Open Powershell on the local system
## Log into azure account with "az login"
# Create a resource group with "az group create --resource-group with location in east us
## Create resource group with "az group create --resource-group webtierRG --location eastus"
![resource group](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/9b393715-7919-4786-a5b1-788bf1c9b8a7)
# Create an azure virtual network with a front end subnet as follows;
## az network vnet creat --resource-group --webtierRG --name threetiervnet --address-prefix 10.1.0.0/16 --subnet-name webvnet --subnet-prefix 10.1.2.0/24
![subnet 1](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/d3e593a4-a928-41b3-8622-1ee8340e70a9)
# Create application subnet called appsubnet:
## az network vnet subnet create --resource-group WebtierRG --vnet-name --threetiervnet webnet --name appsubnet --address-prefix 10.1.2.0/24
![subnet 2](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/3caaadf9-4920-41c0-b71a-c69f7d6806dd)
# Create an database vnet called datavnet:
## Create datanet using "az network vnet subnet create --resource-group WebtierRG --vnet-name threetiervnet --name datanet --address-prefix 10.1.3.0/24
![create subnets](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/1c591e32-7617-4321-a8b9-cecbd230b7ad)
# Open the azure portal to create the Network Security group (NSG)
## Deploy virtual machines into the respective subnets
![web vm1](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/59c469a9-e50a-4d4e-96e6-d8997a90fdf0)
![webvm2](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/1c2ccd9b-f96e-4a34-a5fd-c3c145a023a9)
![web vm rule](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/ac00b885-3bc8-4f25-bb2d-9e7e95e89a5e)
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
![webtierRG (5)](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/78f48c7d-f7b5-4874-9566-d358d5933a21)
![2023-12-09_15h55_14](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/57612923-cfe0-427d-9aa9-fc997358a877)
![2023-12-09_15h55_56](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/a7414363-705a-4877-865a-d46e3a632741)
![2023-12-09_22h22_58](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/a5673414-b279-48bf-b545-dfa702cc9043)
![load balancer](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/0feac11b-b0cf-42d4-8e4c-7d8bbba8b732)
![2023-12-09_22h28_54](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/841d8454-8904-44d7-b1dc-cd27ae1c3728)
![2023-12-09_22h29_08](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/7fbeda11-3d04-4196-8073-e3c14f3ebc84)
![2023-12-09_22h20_31](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/95b1c21a-5ba6-42e3-838e-be98907794a7)
![2023-12-09_22h20_31](https://github.com/oyedolakunle/Implementing-multi-tier-web-in-Azure/assets/145802011/6db8dd6a-3a45-4213-8518-6a82bef76db5)




















