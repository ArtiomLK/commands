# PowerShell

| Command                                                            | Description                      |
| ------------------------------------------------------------------ | -------------------------------- |
| `Connect-AzAccount`                                                | login to azure with your account |
| `Get-AzSubscription`                                               | -                                |
| `Set-AzContext -Subscription xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` | use subscriptionID               |
| `Get-AzContext`                                                    | -                                |
| `Get-AzResourceGroup \| Format-Table`                              | -                                |
| `Get-AzLocation \| Format-Table -Property Location, DisplayName`   | -                                |

## Index

- [Create RG][100]

## Create RG

Run the following commands in PowerShell to create an Azure Resource Group

```PowerShell
# Replace the following required Azure Resource Group variables
$rg = @{
    Name = 'your-rg-name'
    Location = 'EastUS2'
}

# Create an Azure ResourceGroup
New-AzResourceGroup @rg
```

## Additional Resources

- [MS | Docs | New-AzResourceGroup][1]
- [MS | Docs | Get-AzLocations][2]

<!-- Reference Links -->

[1]: https://docs.microsoft.com/en-us/powershell/module/az.resources/new-azresourcegroup?view=azps-5.7.0
[2]: https://docs.microsoft.com/en-us/powershell/module/az.resources/get-azlocation?view=azps-5.7.0
[100]: #create-rg
