# Fully defined Bootstrapping Server

Note it take at least 5 minutes to run cloud-init after bootup.

Reference links [here](https://docs.microsoft.com/en-gb/azure/virtual-machines/linux/using-cloud-init)

For automatic configuration also [here](https://docs.microsoft.com/en-gb/azure/virtual-machines/linux/tutorial-automate-vm-deployment)

## Creation using Microsoft Adapted

After logging in to az cli, run the command:

```bash
make server
```

Deleting and clearing up afterwards:

```bash
make destroy
```