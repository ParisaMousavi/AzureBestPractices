# Azure Samples


## Create Site-to-Site VPN
The VPN is used for transmit the confidential values between cloud and on-prem.
![alt](pics/3-network-topology-used-in-exercise.svg)
The az script to create the infrastructure above is available [here](site-to-site/script.azcli).

## Encrypt Storage Data at Rest with customer-managed key

The prerequisites are 
- Storage Account with managed identity
- Azure Key Vault with a Key
- Set the access policy for Storage Account on KeyVault
The az script to create it is available [here](customer-managed-key/script.azcli).
