# az-pipelines-cli-demo
Demoing $ az pipelines CLI commands for Azure DevOps Services
Official documentation here: https://docs.microsoft.com/en-us/cli/azure/pipelines

Install the Azure DevOps CLI tool (based on Azure CLI):
```bash
az extension add --name azure-devops
```
Login to the Azure DevOps account:
```bash
az login
```
Setup the default organisation and project for the below commands (please change with your own parameters):
```bash
az devops configure --defaults organization="https://dev.azure.com/agromart/" project="AzureDevOps_Workshop"
```
Create a DevOps project:
```bash
az devops project create --name "CLI_Demo2" --visibility "public"

```
List all projects within specified organisation:
```bash
az devops project list --organization "https://dev.azure.com/agromart/" -o table
```
Delete devops project: 
```bash
az devops project delete --organization "https://dev.azure.com/agromart/" --id <project id gotten from list projects command> --yes
```
List pipelines within specified organisation and project:
```bash
az pipelines list -o table --org "https://dev.azure.com/agromart/" --project "AzureDevOps_Workshop"
```
List pipelines from the default organisation and project:
```bash
az pipelines list
```
Format the output to a table format instead of JSON: 
```bash
az pipelines list -o table
```
List variables from a specific pipeline (please change with your own parameter):
```bash
az pipelines variable list --pipeline-name "azure-infra-devops-support-community.terraform-migration"
```
List variable groups in JSON format:
```bash
az pipelines variable-group list 
```
List variable groups in table format:
```bash
az pipelines variable-group list -o table
```
List variables within a specific variable group: 
```bash
az pipelines variable-group variable list --group-id 6
```
List pipelines run history within the default organisation and project:
```bash
az pipelines runs list
```
List pipelines in table format:
```bash
az pipelines runs list -o table
```
