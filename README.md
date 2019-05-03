# aks-containerized-solutions

Create containerized solutions with Azure Kubernetes Service (AKS).

![after](https://user-images.githubusercontent.com/3911650/57160414-f5a87480-6da5-11e9-9cdb-5386f47dbd94.png)

## Getting Started

An Azure RM template is included in `infrastructure/` to create the environment:

<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Flrakai%2Faks-containerized-solutions%2Fmaster%2Finfrastructure%2Farm-template.json">
    <img src="https://camo.githubusercontent.com/536ab4f9bc823c2e0ce72fb610aafda57d8c6c12/687474703a2f2f61726d76697a2e696f2f76697375616c697a65627574746f6e2e706e67" data-canonical-src="http://armviz.io/visualizebutton.png" style="max-width:100%;">
</a> 

Using Azure PowerShell, do the following to provision the resources:

```ps1
.\New-Lab.ps1
```

Alternatively, you can perform a one-click deploy with the following button:

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Flrakai%2Faks-containerized-solutions%2Fmaster%2Finfrastructure%2Farm-template.json">
    <img src="https://camo.githubusercontent.com/9285dd3998997a0835869065bb15e5d500475034/687474703a2f2f617a7572656465706c6f792e6e65742f6465706c6f79627574746f6e2e706e67" data-canonical-src="http://azuredeploy.net/deploybutton.png" style="max-width:100%;">
</a>

## Following Along

1. Clone the Git repository in Azure Cloud Shell

1. Create an Azure Container Registry

1. Create an ACR quick task to build and push the app to the registry (`az acr build`)

1. Deploy the application using the Kuberentes manifest file in `src/app.yaml`

    1. Substitute the `{{acr_name}}` and `{{dns_zone}}` with their actual values in your environment

## Tearing Down

When finished, remove the Azure resources with:

```ps1
.\Remove-Lab.ps1
```