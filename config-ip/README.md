
- [Design IP Addressing](#design-ip-addressing)
  - [Introduction](#introduction)
  - [Scenario](#scenario)
  - [Architecture](#architecture)

# Design IP Addressing

## Introduction
I will implement three virtual networks and subnets to support resources in those virtual networks.

## Scenario

The **CoreServicesVnet** virtual network is deployed in the **US West** region.
* This virtual network will have the largest number of resources. 
* It will have connectivity to on-premises networks through a VPN connection. 
* This network will have web services, databases, and other systems that are key to the operations of the business. 
* Shared services, such as Azure Active Directory (Azure AD) domain controllers and DNS also will be located here. 
* A large amount of growth is anticipated, so a large address space is necessary for this virtual network.

[Deployment with CLI](deploy-coreservicevnet.azcli)

The **ManufacturingVnet** virtual network is deployed in the **North Europe** region, near the location of your organization's manufacturing facilities. 
* This virtual network will contain systems for the operations of the manufacturing facilities. 
* The organization is anticipating a large number of internal connected devices for their systems to retrieve data from, such as temperature, and will need an IP address space that it can expand into.

[Deployment with CLI](deploy-manufacturingvnet.azcli)

The **ResearchVnet** virtual network is deployed in the **West India** region, near the location of the organization's research and development team. 
* The research and development team uses this virtual network. 
* The team has a small, stable set of resources that is not expected to grow. 
* The team needs a small number of IP addresses for a few virtual machines for their work.

[Deployment with CLI](deploy-researchvnet.azcli)

## Architecture

![alt](pics/5-design-implement-vnet-peering.svg)




























Source:https://docs.microsoft.com/en-us/learn/modules/design-ip-addressing-for-azure/5-exercise-implement-vnets
