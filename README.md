# loggingdemo_infra

# Set up Flux

## Setting up infra as code
https://fluxcd.io/docs/get-started/

### Pre req

1. choco install kind
2. choco install flux

### Create cluster
kind create cluster.

### Set up variables 

set GITHUB_TOKEN eg 
setx GITHUB_TOKEN="ghp_etc”
set GITHUB_USER

To check can use $env:VAR_NAME in PS or echo %VAR_NAME% in cmd

https://www.shellhacks.com/windows-set-environment-variable-cmd-powershell/

### Flux pre check

flux check --pre

### Bootstrap
flux bootstrap github --owner=$GITHUB_ORG --repository=loggingdemo_infra --path ./clusters/flux --private=false --branch=main --personal=false
### Clone created repo
git clone https://github.com/JPDemo/loggingdemo_infra.git
### Verify whats created on K8
kubectl get all -n flux-system

# Install Kuztomize

choco install kustomize