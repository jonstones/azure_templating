# Inventory test with external parameters

Run the playbook

```bash
ansible-playbook -i ./inventory/networks.yml ./network.yml
```

Clean up between runs to iteratively test:

```bash
az group delete --name rg-az-we-hub1-hndovr-ntw-1 --yes ; \
for item in `az group list --output table | grep hndovr | awk '{ print $1 }'` ; \
do az group delete --name ${item} --yes --no-wait ; done
```

Checking status of resource groups:

```bash
az group list --output table
```

Short-cutting to interesting tasks:

```bash
ansible-playbook -i ./inventory/networks.yml ./network.yml \
--step \
--start-at-task='Networks | Create spoke to hub virtual network peering'
```
