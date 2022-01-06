# DevOpsAgent

Deploy Agent for Azure DevOps

In azure run following in the azure-cli

```bash
cd clouddrive

git clone https://github.com/jesperberth/devopsagent/

cd azure

ansible-galaxy install -r requirements.yml

ansible-playbook 00_azure_class_setup.yml

ansible-playbook -u USERNAME -i inv.azure_rm.yml 01_azure_class_setup.yml

```
