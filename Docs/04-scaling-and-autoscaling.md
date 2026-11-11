
# 04 - Application Scaling and Autoscaling

## Objective
Configure and monitor application instances using IBM Cloud Code Engine.

## 1. Check application status

```bash
ibmcloud ce app get --name listing -q

ibmcloud ce app get --name websites -q
```

Check:
- Running instances
- Minimum scale
- Maximum scale
- Application revision
- Application readiness

## 2. Configure Listing minimum scale

```bash
ibmcloud ce app update --name listing --min 2
```

This configures a minimum of two application instances.

## 3. Configure Websites minimum scale

```bash
ibmcloud ce app update --name websites --min 2
```

This configures a minimum of two application instances.

## 4. Configure maximum scale (optional)

```bash
ibmcloud ce app update --name websites --max-scale 10
```

This sets the maximum number of instances to ten.

## 5. Verify scaling configuration

```bash
ibmcloud ce app get --name listing -q

ibmcloud ce app get --name websites -q
```

Look for:

```text
Minimum Scale: 2
Running Instances: 2
```

## 6. Understand scaling behaviour

| Minimum scale | Behaviour |
|---|---|
| 0 | Can scale to zero when idle |
| 1 | Maintains at least one instance |
| 2 | Maintains at least two instances |

## Key concepts learned

- Horizontal scaling
- Minimum and maximum instances
- Scale-to-zero
- Cold starts
- Application revisions
- Resource allocation
- High availability considerations
