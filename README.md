# Azure Pipelines Linux Agent

Based on https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/docker

Build using the following command:

    docker build -t paulvaillant/azure-pipelines-agent:latest .

Run using the following command:

    docker run -e AZP_URL=https://dev.azure.com/<your_organization> -e AZP_TOKEN=<PAT token> paulvaillant/azure-pipelines-agent:latest

Note: if docker tasks are required, /var/run/docker.sock must be mapped

The PAT token is generated using this process: https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/v2-linux#permissions

## Environment Variables:

Variable Name   | Description
-----------------------------
AZP_URL         | The URL of the Azure DevOps or Azure DevOps Server instance
AZP_TOKEN	    | Personal Access Token (PAT) granting access to AZP_URL
AZP_AGENT_NAME	| Agent name (default value: the container hostname)
AZP_POOL	    | Agent pool name (default value: Default)
AZP_WORK	    | Work directory (default value: _work)