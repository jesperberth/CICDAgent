# Install steps

## Ubuntu

Prepare in GitHub

Create a PAT (Personal Access Token)

```bash

ansible-playbook -i inv.azure_rm.yml --key-file ~/.ssh/Testkey.pem install_github_runner.yml -e "ansible_user=azureuser"

```
