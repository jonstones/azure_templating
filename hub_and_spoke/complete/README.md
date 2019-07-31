# Inventory test with external parameters

Run the playbook

```bash
ansible-playbook -i ./inventory/networks.yml ./network.yml
```

Clean up between runs to iteratively test:

```bash
for item in `az group list --output table | grep hndovr | awk '{ print $1 }'` ; do az group delete --name ${item} --yes --no-wait ; done
```

Checking status of resource groups:

```bash
az group list --output table
```
