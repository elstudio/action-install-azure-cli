# action-install-azure-cli

Composite action to install the Azure CLI on Ubuntu. 

Installs or updates the azure-cli tool on Ubuntu or other Debian-based OS using the instructions here: https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt

GitHub-hosted actions runners already have `az` installed, so you probably only need this action to install azure-cli on a self-hosted or Premium runner.

### Usage

```yaml
name: Deploy

on:
  push:
    branches: [ main ]
  workflow_dispatch:

jobs:

  deploy:
    # Replace `self-hosted-ubuntu` with the label of your self-hosted runner(s)
    runs-on: self-hosted-ubuntu
    steps:
      # Install azure-cli
      - uses: elstudio/action-install-azure-cli@v1
      # Now run whatever steps require the `az` command line utility 
      - uses: azure/webapps-deploy@v2
      # for example
```