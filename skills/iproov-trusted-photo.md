---
name: iproov-trusted-photo
description: "Enrol or verify a user against a trusted photo (e.g. an ID document image) using multipart upload."
api: iproov:iproov-rest-api
operations:
- userEnrolServerToken
- userEnrolImage
- userVerifyImage

generated: '2026-10-18'
method: generated
source: openapi/iproov-openapi.yml
---

# Enrol or verify a user against a trusted photo (e.g. an ID document image) using multipart upload.

1. To enrol from a trusted photo, first obtain an enrol token with `userEnrolServerToken`, then call `userEnrolImage` (POST /claim/enrol/image, multipart/form-data) with `api_key`, `secret`, `rotation`, `image`, `token` (optional `source`).
2. To check a user against a trusted photo, call `userVerifyImage` (POST /claim/verify/image, multipart/form-data) with `api_key`, `secret`, `user_id`, `resource`, `image` (optional `source`).

## Conventions
- Base URL is regional (`https://<region>.rp.secure.iproov.me/api/v2`); use the Service Location from iPortal.
- Error responses documented in the spec: 400, 401, 403, 404, 429 (token endpoints and image endpoints), 500. Back off on 429.
- The spec documents no idempotency keys; do not blindly retry POSTs that mint or validate tokens.
