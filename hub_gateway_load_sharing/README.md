# Sharing two VPN Gateways in Active and Active State

Please note the prerequisites must be met in order to run the playbook.

Please also note owing to multiple python interpreters being present, the
interpreter has been explicitly set within the ```ansible.cfg``` file, you
may have to remove this to run thie playbook correctly on your own system.

## Prerequities

Ansible 2.8, and an active Service Principal Name (SPN) with network contributor
rights to the relevant subscription.

## Evironemntal variables

Ensure the environmental variables are set correctly.  Note, unlike terraform,
with Asnible there is no ```_id``` on the end of the secret and tenant variables

```bash
export AZURE_SUBSCRIPTION_ID="some_subscription"
export AZURE_CLIENT_ID="some_client"
export AZURE_SECRET="some_secret"
export AZURE_TENANT="some_tenant"
```

These are taken from when the SPN is registered to the susbscription.

Ensure these are set, or better still added to ```~/.bash_profile```  or ```~/.bash_rc```
or whatever linux system being used.  

## Create Basic Networks in Azure

Route tables are attached to subnets, not the other way around.  A basic network is
created with the following playbook in order to test the route attachment.

```bash
ansible-playbook -i ./inventory/networks.yml ./create_networks.yml
```

Routing can be manipulated afterwards:

```bash
ansible-playbook -i ./inventory/networks.yml ./create_routing.yml
```
