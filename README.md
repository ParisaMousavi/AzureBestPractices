- [Azure Samples](#azure-samples)
  - [Azure Infrastructure](#azure-infrastructure)
    - [Create Site-to-Site VPN](#create-site-to-site-vpn)
    - [Azure IP config](#azure-ip-config)
  - [Azure Infrastructure Deployment](#azure-infrastructure-deployment)
    - [Deploy Azure Resource Manager templates](#deploy-azure-resource-manager-templates)
  - [Azure Data Encryption](#azure-data-encryption)
    - [Encrypt Storage Data at Rest with customer-managed key](#encrypt-storage-data-at-rest-with-customer-managed-key)
  - [Azure Virtual Machines](#azure-virtual-machines)
    - [Create an image from a generalized VM](#create-an-image-from-a-generalized-vm)


# Azure Samples

## Azure Infrastructure

### Create Site-to-Site VPN
The VPN is used for transmit the confidential values between cloud and on-prem.
![alt](pics/3-network-topology-used-in-exercise.svg)
The az script to create the infrastructure above is available [here](site-to-site/script.azcli).

### Azure IP config
Two types of IP addresses are available on Azure
- **Private IP Address**
- **Public IP Address** (these addreses have two possible type on Azure)
  - **Static**: has been created already and will be assigned to a resource but when the resource is deleted, the IP won't get deleted.
  - **dynamic**: is created and assigned to a resource when needed. When the resource is deleted, the IP is deleted as well.

The az script and more info are availble [here](config-ip/README.md).

## Azure Infrastructure Deployment

We have serveral available provisioing solutions:
- Custome scripts (VMs)
- Desired State Configuration Extensions (VMs)
- Chef Server
- Terraform (all resources)
- Azure Automation State Configuration
- Azure Resource Manager templates (all resources)

For more info about the other option refer to [Onboarding : Azure Infrastructure deployment](https://multi-cloud-solutions.com/2020/08/11/onboarding-azure-infrastructure-deployment/).

### Deploy Azure Resource Manager templates
1. We can use the Quick Start Templates to create our required template
2. We have to validate the template
3. Deploy the template via Azure UI, Powershell, CLI

The commands for validating and deploying via CLI are available in the script [here](deploy-arm-template/script.azcli). 

**Extend VM Configuration after deploy**
We can use `Custom Script Extension` for VMs to install something or apply some changes after deploy the VM.

In the Script [here](deploy-arm-template/script-custom-script-extension.azcli) we see we can either run the `Custome Script Extension` via CLI or add it to the ARM template.

## Azure Data Encryption

### Encrypt Storage Data at Rest with customer-managed key

The prerequisites are 
- Storage Account with managed identity
- Azure Key Vault with a Key
- Set the access policy for Storage Account on KeyVault
The az script to create it is available [here](customer-managed-key/script.azcli).


## Azure Virtual Machines

### Create an image from a generalized VM
For creating a VM Image, the vm have to be generalized. This is the [link](generalizing-vm/script.azcli) to the code for generalizing.

It can be done via Azure UI as well.