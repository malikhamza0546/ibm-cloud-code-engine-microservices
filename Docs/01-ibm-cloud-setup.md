
# 01 - IBM Cloud Setup

## Objective
Prepare the IBM Cloud CLI environment and select the Code Engine project.

## 1. Login to IBM Cloud

```bash
ibmcloud login --sso
```

Use your IBM Cloud account to authenticate.

## 2. Install Code Engine CLI plugin

```bash
ibmcloud plugin install code-engine
```

This enables Code Engine commands through the IBM Cloud CLI.

## 3. Check installed plugins

```bash
ibmcloud plugin list
```

## 4. Select the Code Engine project

```bash
ibmcloud ce project select --name "Code Engine - sn-labs-malikhamza05"
```

This selects the project in which applications will be deployed.

## 5. Verify project information

```bash
ibmcloud ce project get --name "Code Engine - sn-labs-malikhamza05"
```

Displays project information, resource quotas, CPU, memory and active instances.

## Technologies
- IBM Cloud CLI
- IBM Cloud Code Engine
- IBM Container Registry
