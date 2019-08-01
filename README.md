# Azure Templating

General templates to reduce the mundane aspects of public cloud

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