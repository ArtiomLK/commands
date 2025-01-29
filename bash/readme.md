# Bash

| Command                                                                       | Description                                              |
| ----------------------------------------------------------------------------- | -------------------------------------------------------- |
| `az login`                                                                    | login to azure with your account                         |
| `az login --tenant xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`                      | login to azure with your account to specific tenant      |
| `az account list --output table`                                              | display available subscription                           |
| `az account set --subscription xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`          | use subscriptionID                                       |
| `az account show --output table`                                              | check the subscriptions currently in use                 |
| `az group list -o table`                                                      | List all rg                                              |
| `az account list-locations -o table`                                          | List available regions                                   |
| `az aks get-versions --location eastus2 -o table`                             | List AKS versions by region                              |
| `export MSYS_NO_PATHCONV=1`                                                   | avoids the C:/Program Files/Git/ being appended          |
| `az vm list-skus --location centralus --size Standard_D --all --output table` | Determine which SKUs are available in a location or zone |

## Index

- [Create vnet peering][100]
- [Create RG][101]
- [Create App Registration][102]
- [Register Resource Provider][103]

## Create vnet peering

```bash
# ------------------------------------------------------------------------------------------------
# Create vnet peering
# ------------------------------------------------------------------------------------------------
# VNET_1 Variables
vnet1_rg_n="rg-name-1";                             echo $vnet1_rg_n
vnet1_n="vnet-name-1";                              echo $vnet1_n

# VNET_2 Variables
vnet2_rg_n="rg-name-2";                             echo $vnet2_rg_n
vnet2_n="vnet-name-2";                              echo $vnet2_n

VNET_1_ID=$(az network vnet show --resource-group $vnet1_rg_n --name $vnet1_n --query id --out tsv); echo $VNET_1_ID
VNET_2_ID=$(az network vnet show --resource-group $vnet2_rg_n --name $vnet2_n --query id --out tsv); echo $VNET_2_ID

# VNET PEER from VNET_1 to VNET_2
az network vnet peering create \
--name "peer-$vnet1_n-to-$vnet2_n" \
--resource-group $vnet1_rg_n \
--vnet-name $vnet1_n \
--remote-vnet $VNET_2_ID \
--allow-vnet-access

# VNET PEER from VNET_2 to VNET_1
az network vnet peering create \
--name "peer-$vnet2_n-to-$vnet1_n" \
--resource-group $vnet2_rg_n \
--vnet-name $vnet2_n \
--remote-vnet $VNET_1_ID \
--allow-vnet-access
```

## Create RG

```bash
sub_id='xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx';                          echo $sub_id      # must update
app="alz-bas";                                                          echo $app
env="dev";                                                              echo $env
l="eastus";                                                             echo $l
rg_n="rg-$app-$env-$l";                                                 echo $rg_n
tags="project=bicephub env=$env architecture=alz";                      echo $tags

az group create \
--subscription $sub_id \
--name $rg_n \
--location $l \
--tags $tags
```

## Create App Registration

```bash
sub_id='xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx';                          echo $sub_id      # must update
rg_app_n="rg-appName";                                                  echo $rg_app_n
app_registration_n="sc-rg-appName";                                     echo $app_registration_n

# ------------------------------------------------------------------------------------------------
# Create app registration
# ------------------------------------------------------------------------------------------------
az ad app create \
--display-name $app_registration_n

SC_APP_CLIENT_ID=$(az ad app create --display-name $app_registration_n --query appId --output tsv); echo $SC_APP_CLIENT_ID
SC_APP_OBJECT_ID=$(az ad app show --id $SC_APP_CLIENT_ID --query id --output tsv); echo $SC_APP_OBJECT_ID

# Create an AAD service principal
az ad sp create \
--id $SC_APP_OBJECT_ID

# Look up a service principal
SC_SP_OBJECT_ID=$(az ad sp show --id $SC_APP_CLIENT_ID --query id --output tsv); echo $SC_SP_OBJECT_ID

# Get RG ID
APP_RG_ID=$(az group show --subscription $sub_id --name $rg_app_n --query id -o tsv); echo $APP_RG_ID

# OPTION 1 - Assign SC Contributor RBAC on RG
az role assignment create \
--assignee $SC_SP_OBJECT_ID \
--role "Contributor" \
--scope $APP_RG_ID

# OPTION 2 - Assign SC Contributor RBAC on SUB
az role assignment create \
--assignee $SC_SP_OBJECT_ID \
--role "Contributor" \
--scope "/subscriptions/$sub_id"
```

## Register Resource Provider

```bash
sub_id='xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx';                          echo $sub_id      # must update

RESOURCE_PROVIDERS=(
Microsoft.CognitiveServices
Microsoft.Cdn
Microsoft.Cache
Microsoft.Network
Microsoft.KeyVault
Microsoft.Web
Microsoft.Compute
Microsoft.ContainerRegistry
Microsoft.Storage
microsoft.insights
); echo ${RESOURCE_PROVIDERS[@]}

for res_provider in "${RESOURCE_PROVIDERS[@]}"
do
  echo "Registering $res_provider"
  az provider register --namespace $res_provider --subscription $sub_id
done
```

## Start and Stop agw

```bash
az network application-gateway stop --id "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/rg-name/providers/Microsoft.Network/applicationGateways/agw-name"
az network application-gateway start --id "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/rg-name/providers/Microsoft.Network/applicationGateways/agw-name"
```

## Create NSG

```bash
rg_n="rg-myapp-dev-eastus2";                                        echo $rg_n
nsg_n="nsg-myapp-default-dev-eastus2";                              echo $nsg_n
l="eastus2";                                                        echo $l
tags="Env=Dev Project=myapp CostCenter=1234";                       echo $tags

az network nsg create \
--resource-group $rg_n \
--name $nsg_n \
--location $l \
--tags $tags
```

### Additional Resources

- App Registration
- [MS | Learn | Register a client application using CLI and REST API][1]
- SKU not available
- [MS | Learn | Resolve errors for SKU not available][2]
- Register Resource Provider
- [MS | Learn | az provider register][3]

[1]: https://learn.microsoft.com/en-us/azure/healthcare-apis/register-application-cli-rest
[2]: https://learn.microsoft.com/en-us/azure/azure-resource-manager/troubleshooting/error-sku-not-available
[3]: https://learn.microsoft.com/en-us/cli/azure/provider?view=azure-cli-latest#az-provider-register
[100]: #create-vnet-peering
[101]: #create-rg
[102]: #create-app-registration
[103]: #register-resource-provider
