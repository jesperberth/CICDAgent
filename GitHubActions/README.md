# Install steps

## GitHub

### Part 1

Prepare in GitHub

Create a PAT (Personal Access Token)

- repo
- workflow
- admin:enterprise

### Part 2

Create secrets in GitHub repo

AZURE_KEYVAULT = name of the Azure Keyvault

AZURE_CREDENTIALS =

```bash

{
    "clientId": "<GUID>",
    "clientSecret": "<GUID>",
    "subscriptionId": "<GUID>",
    "tenantId": "<GUID>
}

```

## Azure Keyvault

Create keyvault in azure

Credentials need get, list, set on secret

Create secrets

- GitHubPAT
- azureclientid
- azuresecret
- azuresubid
- azuretenant

```bash

ssh-keygen -t rsa -q -f "server-key" -N ""

VAULT=vaultname

az keyvault secret set --vault-name $VAULT -n server-key-priv -f '~/.ssh/server-key'

az keyvault secret set --vault-name $VAULT -n server-key-pub -f '~/.ssh/server-key.pub'

```

## Ubuntu 20.04 LTS

Deploy azure vm with Ubuntu Server 20.04 LTS

tag environment:githubrunner

Use ssh key pair

```bash

ansible-playbook -i inv.azure_rm.yml --key-file ~/.ssh/Testkey.pem install_github_runner.yml -e "ansible_user=azureuser"

```
