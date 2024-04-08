# Import API on Azure API Management Service Instance

This template provides a streamlined way to import API on Azure API Management Service Instance using Azure Pipelines.

## Parameters

**azureSubscription (type: string)**: The name of the Azure subscription service connection. <br>
**resourceGroup (type: string)**: The name of the Azure Resource Group. <br>
**apiId (type: string)**: Unique ID for your API.<br>
**serviceName (type: string)**: Name of your Azure API Management Instance. <br>
**path (type: string)**: Relative URL uniquely identifying your API and all of its resource paths. <br>
**displayName (type: string)**: Display name of API. <br>
**specificationUrl (type: string)**: URL specified to import the API. <br>
**specificationFormat (type: string)**: Format of your API (eg. OpenApi). <br>

## Usage

To use this template, include the following YAML snippet in your Azure Pipelines:

```yaml
resources:
  repositories:
    - repository: API
      type: github
      name: GitHubUserName/repoName
      ref: 'respective-branch-name'            
      endpoint: 'ServiceConnectionForgitHub'
 
jobs:
  - job: Import API
    steps:
    - template: path/to/your/template/importAPI.yml@API
      parameters:
        azureSubscription: <azure subscription service connection>
        resourceGroup: <name of resource group>
        apiId: <Unique ID for your API>
        serviceName: <Name of your Azure API Management Instance>
        path: <Relative URL uniquely identifying your API and all of its resource paths>
        displayName: <Display name of API>
        specificationUrl: <URL specified to import the API>
        specificationFormat: <Format of your API>
```
Make sure to replace the placeholders (<...>) with your specific values.

## Notes

- Ensure that the necessary Azure service connection (**ServiceConnectionForgitHub**) is set up in your Azure Pipelines project.<br>
- Customize the repository and branch information in the resources section according to your GitHub repository setup.<br>

Adapt and extend this template to suit your specific needs.
