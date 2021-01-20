### Mount File Share on Ubuntu VM
```
# sudo apt-get update -y
# sudo apt-get install -y cifs-utils
# curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
# az login
  Open the link you recieve from above command in your browser and add the Code shared and then login with you account once done, you will get an ouput as shown below
```
### Output
```
[
  {
    "cloudName": "AzureCloud",
    "homeTenantId": "af1b6ff7-ddf1-4bd1-acf5-5b432a4c65c0",
    "id": "312b69f3-480b-46a3-afd6-ae7c053ab0ae",
    "isDefault": true,
    "managedByTenants": [],
    "name": "Pay-As-You-Go",
    "state": "Enabled",
    "tenantId": "af1b6ff7-ddf1-4bd1-acf5-5b432a4c65c0",
    "user": {
      "name": "mayerramesh@gmail.com",
      "type": "user"
    }
  }
]
```
 Check if 445 port if Open, which is needed from communication between SA & Server
 ```
# resourceGroupName="jan-batch"
# storageAccountName="kul"

# This command assumes you have logged in with az login
# httpEndpoint=$(az storage account show \
    --resource-group $resourceGroupName \
    --name $storageAccountName \
    --query "primaryEndpoints.file" | tr -d '"')
# smbPath=$(echo $httpEndpoint | cut -c7-$(expr length $httpEndpoint))
# fileHost=$(echo $smbPath | tr -d "/")

# nc -zvw3 $fileHost 445
 ```
