---
title: Resource Manager template samples for Azure Monitor
description: Deploy and configure Azure Monitor features using Resource Manager templates
author: bwren
ms.author: bwren
services: azure-monitor
ms.topic: sample
ms.date: 05/18/2020
ms.subservice: 
---
# Resource Manager template samples for Azure Monitor

Azure Monitor can be deployed and configured at scale using [Azure Resource Manager template](../azure-resource-manager/templates/template-syntax.md). The following articles provide sample templates for different Azure Monitor features. These samples can be modified for your particular requirements and deployed using any standard method for deploying Resource Manager templates. 

## Deploying the sample templates
The basic steps to use the samples are:

1. Copy the template and save as a JSON file.
2. Modify the parameters for your environment and save as a JSON file.
4. Deploy the template using [any deployment method for Resource Manager templates](../azure-resource-manager/templates/deploy-powershell.md). 

For example, use the following commands to deploy the template and parameters file to a resource group using PowerShell or Azure CLI.


```powershell
Connect-AzAccount
Select-AzSubscription -SubscriptionName my-subscription
New-AzResourceGroupDeployment -Name AzureMonitorDeployment -ResourceGroupName my-resource-group -TemplateFile azure-monitor-deploy.json -TemplateParameterFile azure-monitor-deploy.parameters.json
```

```azurecli
az login
az deployment group create \
    --name AzureMonitorDeployment \
    --resource-group ResourceGroupofTargetResource \
    --template-file azure-monitor-deploy.json \
    --parameters azure-monitor-deploy.parameters.json
```

## List of sample templates

- [Agents](agents/resource-manager-agent.md) - Deploy and configure Log Analytics agent and diagnostic extension.
- Alerts
  - [Log alert rules](alerts/resource-manager-alerts-log.md) - Alerts from log queries and Azure activity log.
  - [Metric alert rules](alerts/resource-manager-alerts-metric.md) - Alerts from metrics using different kinds of logic.
- [Application Insights](app/resource-manager-app-resource.md)
- [Diagnostic settings](essentials/resource-manager-diagnostic-settings.md) - Create diagnostic settings to forward logs and metrics from different resource types.
- [Log queries](logs/resource-manager-log-queries.md) - Create saved log queries in a Log Analytics workspace.
- [Log Analytics Workspace](logs/resource-manager-workspace.md) - Create Log Analytics workspace and configure collection of different data sources from Log Analytics agent.
- [Workbooks](visualize/resource-manager-workbooks.md) - Create workbooks.
- [Azure Monitor for containers](containers/resource-manager-container-insights.md) - Onboard clusters to Azure Monitor for containers.
- [Azure Monitor for VMs](vm/resource-manager-vminsights.md) - Onboard virtual machines to Azure Monitor for VMs.



## Next steps

- Learn more about [Resource Manager templates](../azure-resource-manager/templates/overview.md)