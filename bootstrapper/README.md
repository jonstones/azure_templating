# Fully defined Bootstrapping Server

*This section of the repo is currently still in progress and is only partially functional!*

Note it take at least 5 minutes to run cloud-init after bootup.

Reference links [here](https://docs.microsoft.com/en-gb/azure/virtual-machines/linux/using-cloud-init)

For automatic configuration also [here](https://docs.microsoft.com/en-gb/azure/virtual-machines/linux/tutorial-automate-vm-deployment)

## Notes for use

The current users ssh key is read from the local disk and added to the ```authorized_key``` file.  The ```cloud-init.yml``` is also read from the local disk, from the present working directory, being from the respository.

## Creation using Microsoft Adapted

After logging in to az cli, run the command:

```bash
make bootstrap
```

Deleting and clearing up afterwards:

```bash
make destroy
```