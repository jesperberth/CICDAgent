# DevOpsAgent

Deploy Agent for Azure DevOps

In azure run following in the azure-cli

```bash
cd clouddrive

git clone https://github.com/jesperberth/devopsagent/

cd azure

ansible-galaxy install -r requirements.yml

ansible-playbook 00_azure_class_setup.yml
```

```bash

az ad sp create-for-rbac --name ansibleuser --role Contributor



```
