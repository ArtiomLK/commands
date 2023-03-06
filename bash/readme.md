# Bash

| Command                                                              | Description                                     |
| -------------------------------------------------------------------- | ----------------------------------------------- |
| `az login`                                                           | login to azure with your account                |
| `az account list --output table`                                     | display available subscription                  |
| `az account set --subscription xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` | use subscriptionID                              |
| `az account show --output table`                                     | check the subscriptions currently in use        |
| `az group list -o table`                                             | List all rg                                     |
| `az account list-locations -o table`                                 | List available regions                          |
| `az aks get-versions --location eastus2 -o table`                    | List AKS versions by region                     |
| `export MSYS_NO_PATHCONV=1`                                          | avoids the C:/Program Files/Git/ being appended |

## Create a vnet peering

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
