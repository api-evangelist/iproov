---
name: iproov-manage-users
description: "Read, rename or delete a user persona using an OAuth 2 bearer token."
api: iproov:iproov-rest-api
operations:
- generateToken
- userGet
- userUpdate
- userDelete

generated: '2026-10-18'
method: generated
source: openapi/iproov-openapi.yml
---

# Read, rename or delete a user persona using an OAuth 2 bearer token.

1. Call `generateToken` (POST /{api_key}/access_token, HTTP Basic, form-encoded `grant_type`, optional `scope`) to obtain a bearer token.
2. `userGet` (GET /users/{existing_user_id}) needs scope `user-read`.
3. `userUpdate` (PUT /users/{existing_user_id}) and `userDelete` (DELETE) need scope `user-write`. Deletion is destructive; confirm before calling.

## Conventions
- Base URL is regional (`https://<region>.rp.secure.iproov.me/api/v2`); use the Service Location from iPortal.
- Error responses documented in the spec: 400, 401, 403, 404, 429 (token endpoints and image endpoints), 500. Back off on 429.
- The spec documents no idempotency keys; do not blindly retry POSTs that mint or validate tokens.
