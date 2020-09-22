- [Azure Samples](#azure-samples)
  - [Azure Infrastructure](#azure-infrastructure)
    - [Create Site-to-Site VPN](#create-site-to-site-vpn)
    - [Azure IP config](#azure-ip-config)
  - [Azure Data Encryption](#azure-data-encryption)
    - [Encrypt Storage Data at Rest with customer-managed key](#encrypt-storage-data-at-rest-with-customer-managed-key)


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

## Azure Data Encryption

### Encrypt Storage Data at Rest with customer-managed key

The prerequisites are 
- Storage Account with managed identity
- Azure Key Vault with a Key
- Set the access policy for Storage Account on KeyVault
The az script to create it is available [here](customer-managed-key/script.azcli).
