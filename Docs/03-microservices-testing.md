
# 03 - Microservices Testing

## Objective
Test the deployed Flask microservices using HTTP requests and curl.

## 1. Listing Microservice

Public endpoint:

```text
https://listing.2h19ldutjn6f.us-south.codeengine.appdomain.cloud
```

Test university search:

```bash
curl "https://listing.2h19ldutjn6f.us-south.codeengine.appdomain.cloud/colleges/Trinity"
```

## 2. Websites Microservice

Public endpoint:

```text
https://websites.2h19ldutjn6f.us-south.codeengine.appdomain.cloud
```

Test university website lookup:

```bash
curl "https://websites.2h19ldutjn6f.us-south.codeengine.appdomain.cloud/websites/Trinity%20College%20of%20Music"
```

Test keyword search:

```bash
curl "https://websites.2h19ldutjn6f.us-south.codeengine.appdomain.cloud/websites/Trinity"
```

## 3. Internal Microservice URLs

Listing:

```text
http://listing.2h19ldutjn6f.svc.cluster.local
```

Websites:

```text
http://websites.2h19ldutjn6f.svc.cluster.local
```

These URLs are used for communication between applications inside the same Code Engine project.

## 4. Testing concepts

- HTTP GET requests
- REST-style endpoints
- Public application URLs
- Internal service discovery
- URL encoding
- Microservice communication

## Expected result

The listing service returns matching university information.

The websites service returns the website URLs associated with matching universities.
