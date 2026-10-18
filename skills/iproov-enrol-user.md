---
name: iproov-enrol-user
description: Enrol a new user through a trusted photo and activate their account.
api: openapi/iproov-openapi.yml
operations:
- userEnrolServerToken
- userEnrolImage
- userEnrolValidate
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/iproov-openapi.yml ; every operationId checked against the contract
---

# iproov-enrol-user

Enrol a new user through a trusted photo and activate their account.

## Steps

1. 1. Generate an enrolment token for the new user using `userEnrolServerToken`
2. 2. Enrol the user through a trusted photo using `userEnrolImage`
3. 3. Validate the enrolment and activate the user using `userEnrolValidate`

## Rules

- Authentication required via basicAuth or oauth2 schemes
- Rate limited to TPS limit as per your contract with HTTP 429 on exhaustion
- All operations use base URL https://<base_url>/api/v2
