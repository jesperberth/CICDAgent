# CICDAgent

## Deploy Agent for Azure DevOps

In azure run following in the azure-cli

Create an ansible vault file devopsagent_info.yml with the content below change the keys to match you environment

```bash

ansible-vault create devopsagent_info.yml

```

```bash
---
account: devopsteam
token: asdfh987asdfhkasdf98dsf
pool: Selfhosted
azuresubid: xxxx-xxxx-xxxx-xxxx-xxxx
azureclientid: xxx-xxx-xxx-xxx
azuresecret: xxxxxxxxxxx
azuretenant: xxxxx-xxxxx-xxxxx
```

```bash
cd clouddrive

git clone https://github.com/jesperberth/devopsagent/

cd azure

ansible-galaxy install -r requirements.yml

ansible-playbook 00_azure_class_setup.yml

ansible-playbook -u USERNAME -i inv.azure_rm.yml 01_azure_class_setup.yml --ask-vault-pass

```

## Deploy Agent for GitHub Actions

