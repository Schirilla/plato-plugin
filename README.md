# Azure Pipeline Demo for Plato Connection

Azure pipeline is using the template to access to Plato and download the existing configuration as xlsx file.
Template has set of parameters to connect to Plato and where to download.
This pipeline is executed in local agent so it requires such configuration


## Agent Configuration in Linux

Create Personal Access Token from following URL:
https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=preview-page

Download the vsagent from following URL:
https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/v2-linux?view=azure-devops 

Do the config:
```
./config.sh --proxyurl $http_proxy --acceptteeeula --agent nhc --url 'https://dev.azure.com/achillschirilla013/' --work _work --projectname 'plato-plugin' --auth PAT --token ${PAT_TOKEN}
```

And run:
```
./run.sh
```

## Pipeline Execution
Run pipeline by entering 2 variables: Nokia Username and Nokia Password. 

After successfully execution of pipeline, the file downloaded from Plato would be located  under /tmp/file.xlsx
