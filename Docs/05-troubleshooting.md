
# 05 - Troubleshooting and Resource Management

## Objective
Understand deployment failures, application revisions and resource quota limitations.

## 1. Check project resource quotas

```bash
ibmcloud ce project get \
  --name "Code Engine - sn-labs-malikhamza05"
```

Check:
- Memory usage
- CPU usage
- Active instances
- Total instances
- Application revisions

## 2. Check application status

```bash
ibmcloud ce app get --name listing -q

ibmcloud ce app get --name websites -q
```

## 3. Memory quota error

Example error:

```text
exceeded quota: 2h19ldutjn6f

requested: requests.memory=4144857600

used: requests.memory=16579430400

limited: requests.memory=20G
```

### Cause

The application update required additional memory, but the project had insufficient available quota.

During deployment, old instances can still be terminating while new revision instances are being created.

### Investigation

1. Check the project memory quota.
2. Check active application revisions.
3. Inspect running and terminating instances.
4. Allow old instances to terminate.
5. Check memory usage again before retrying.

## 4. Inspect application revisions

```bash
ibmcloud ce app get --name listing -q
```

Review:
- Latest revision
- Traffic allocation
- Running instances
- Readiness conditions
- Failed revision events

## 5. Important lessons

- Every application update can create a new revision.
- Old and new instances may temporarily overlap.
- Resource quotas affect deployment and scaling.
- A configured minimum scale does not guarantee deployment success if resources are unavailable.
- Always verify application readiness after an update.

## Key concepts learned

- Cloud resource quotas
- Memory allocation
- Revision management
- Deployment troubleshooting
- Application readiness
- Instance lifecycle management
