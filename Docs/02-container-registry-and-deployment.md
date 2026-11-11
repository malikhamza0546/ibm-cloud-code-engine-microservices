
# 02 - Container Registry and Application Deployment

## Objective
Build container images from source code and deploy Python Flask microservices using IBM Cloud Code Engine.

## 1. Configure registry namespace

```bash
export SN_ICR_NAMESPACE=sn-labs-malikhamza05
```

This environment variable identifies the IBM Container Registry namespace.

## 2. Deploy Listing Microservice

```bash
ibmcloud ce app create \
  --name listing \
  --image us.icr.io/${SN_ICR_NAMESPACE}/listing \
  --registry-secret icr-secret \
  --port 5000 \
  --build-context-dir listing \
  --build-source .
```

## 3. Deploy Websites Microservice

```bash
ibmcloud ce app create \
  --name websites \
  --image us.icr.io/${SN_ICR_NAMESPACE}/websites \
  --registry-secret icr-secret \
  --port 5000 \
  --build-context-dir websites \
  --build-source .
```

## Understanding the deployment options

| Option | Purpose |
|---|---|
| --name | Application name |
| --image | Destination container image |
| --registry-secret | Registry authentication |
| --port | Application listening port |
| --build-context-dir | Directory containing the Docker build context |
| --build-source | Source directory or repository |

## 4. Verify deployed applications

```bash
ibmcloud ce app get --name listing -q

ibmcloud ce app get --name websites -q
```

## What happens during deployment?

1. Code Engine builds the Docker image using the source and Dockerfile.
2. The image is pushed to IBM Container Registry.
3. Code Engine deploys the application.
4. Code Engine creates an application revision.
5. A public application URL becomes available.

## Technologies
- Docker
- IBM Container Registry (ICR)
- IBM Cloud Code Engine
- Python
- Flask
