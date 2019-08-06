.DEFAULT_GOAL := help
SHELL := /bin/bash

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

server: ## Create initialisation server and configure
	@ansible-playbook --inventory inventory/servers.yml ./playbook.yml

destroy: ## Destroy initialisation server
	@az group delete --name "bootstrapper" --no-wait --yes

help:
	@grep -h -E '^[a-zA-Z0-9_-]+:.*?## .*$$' $(MAKEFILE_LIST) | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'