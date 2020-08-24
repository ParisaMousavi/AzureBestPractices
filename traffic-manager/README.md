
# Azure Traffic Manager

## Introduction
Azure Traffic Manager for enhancing **service availability** and **data locality**.

## Scenarion
Let's assume that your music streaming application has an equal distribution of users in the western United States and eastern Asia. You'd like to have a failover version of the app in one region.

The sample application we use for this exercise displays the region it's running in. One of the two instances has higher priority and is the primary endpoint. The other instance has a lower priority and is the failover endpoint. Taking the primary endpoint offline automatically routes all traffic to the failover endpoint.

## Deployment 
```cli
az network traffic-manager profile create \
    --resource-group learn-0b7e0ce9-394c-407c-9d90-09d4fcf4ce72 \
    --name TM-MusicStream-Priority \
    --routing-method Priority \
    --unique-dns-name TM-MusicStream-Priority-$RANDOM
```
* **--routing-method Priority**: Creates the Traffic Manager profile by using the priority routing method.
* **--unique-dns-name**: Creates the globally unique domain name `<unique-dns-name>.trafficmanager.net`. We use the $RANDOM Bash function to return a random whole number to ensure that the name is unique.

There are two script file available for deploying a Traffic Manager Profile with Priority Routing method and a Traffic Manager Profile with Performance Routing method.

[Priority Routing method CLI](traffic-manager-priority.azcli)
[Performance Routing method CLI](traffic-manager-performance.azcli)

For more info about Azure Traffic Manager refer to this [link](https://multi-cloud-solutions.com/2020/08/08/onboarding-azure-application-resilience/#traffic-manager).

Source: https://docs.microsoft.com/en-us/learn/modules/distribute-load-with-traffic-manager/3-exercise-priority-routing