---
name: iproov-verify-user
description: Verify a user's identity through a trusted photo verification process.
api: openapi/iproov-openapi.yml
operations:
- userVerifyServerToken
- userVerifyImage
- userVerifyValidate
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/iproov-openapi.yml ; every operationId checked against the contract
---

# iproov-verify-user

Verify a user's identity through a trusted photo verification process.

## Steps

1. 1. Generate a verification token for the user using `userVerifyServerToken` with required user identification fields
2. 2. Perform the photo verification using `userVerifyImage` with the verification token and image data
3. 3. Validate the verification was successful using `userVerifyValidate` with the verification token

## Rules

- Authentication required via basicAuth or oauth2 schemes
- Rate limited to TPS limit as per your contract with HTTP 429 on exhaustion
- All operations use the base URL https://<base_url>/api/v2
