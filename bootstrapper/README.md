# Fully defined Bootstrapping Server

*This section of the repo is currently still in progress and is only partially functional!*

## Use

This script will be useful for those wanting number of CentOS hosts created, with networking, and
applications being installed without any intervention.

This may be useful if when engaging with a devops team so they may quicky begin builing a
cloud infrastructure.

```bash
make bootstrap
```

Deleting and clearing up afterwards:

```bash
make destroy
```

## Notes for use

This script was run on OSX with multiple versions of python installed, and therefore the python
interpreter has been statically set within the ```ansible.cfg``` file which you may need to
remove on your system (this may be addded to a gitignore file).

Note it take at least 5 minutes to run cloud-init after bootup.

The current users ssh key is read from the local disk and added to the ```authorized_key``` file.  
The ```cloud-init.yml``` is also read from the local disk, which would normally be from the directory
within the cloned repository.

## Powershell

The powershell modules for azure need to be installed manually within powershell

```bash
pwsh
```

Then install the modules and login:

```powershell
Install-Module -Name Az -AllowClobber -Scope CurrentUser -Force
Connect-AzAccount
```

## Reference

Reference links [here](https://docs.microsoft.com/en-gb/azure/virtual-machines/linux/using-cloud-init)

For automatic configuration also [here]
(https://docs.microsoft.com/en-gb/azure/virtual-machines/linux/tutorial-automate-vm-deployment)
