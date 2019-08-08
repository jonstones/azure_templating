.DEFAULT_GOAL := help

prerequisite_check: ## Checks that the credentials environment variables are set
ifndef AZURE_CLIENT_ID
	$(error AZURE_CLIENT_ID is not set)
endif
ifndef AZURE_SUBSCRIPTION_ID
	$(error AZURE_SUBSCRIPTION_ID is not set)
endif
ifndef AZURE_TENANT
	$(error AZURE_TENANT is not set)
endif
ifndef AZURE_SECRET
	$(error AZURE_SECRET is not set)
endif
	@echo "All environment variables are set"

deploy: ## Deploy NFSaaS Infrastructure
	@ansible-playbook -i inventory/ playbooks/networking.yml 
	@ansible-playbook -i inventory/ playbooks/services.yml

deploy_network: ## Deploy NFSaaS Networking
	@ansible-playbook -i inventory/ playbooks/networking.yml

deploy_services: ## Deploy NFSaaS Infrastructure
	@ansible-playbook -i inventory/ playbooks/services.yml

destroy:  ## Destroy all provisioned elements (destroying services first, then infrastrture due to dependencies)
	@for item in `az group list --tag deployment=storage --query [*].name --output tsv` ; do az group delete --name $${item} --no-wait --yes ; done
	
destroy_network: ## Destroy network
	@for item in `az group list --tag service=network --query [*].name --output tsv` ; do az group delete --name $${item} --yes ; done

destroy_services: ## Destroy services
	@for item in `az group list --tag service=nfsservice --query [*].name --output tsv` ; do az group delete --name $${item} --yes ; done

help:
	@grep -h -E '^[a-zA-Z0-9_-]+:.*?## .*$$' $(MAKEFILE_LIST) | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'
