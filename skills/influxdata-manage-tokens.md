---
name: Create and manage API tokens
description: List, create, and revoke InfluxDB API tokens (authorizations) with scoped permissions.
api: openapi/influxdata-cloud-openapi-original.yml
operations: [GetAuthorizations, PostAuthorizations, DeleteAuthorizationsID]
---

# Create and manage API tokens (authorizations)

## Auth
Use an all-access or operator token: `Authorization: Token <INFLUX_API_TOKEN>`.

## Steps
1. **List tokens** — `GetAuthorizations` (`GET /authorizations?org=<org>`).
2. **Create a scoped token** — `PostAuthorizations` (`POST /authorizations`) with `orgID`, `description`, and a `permissions[]` array (each `{action: read|write, resource: {type, orgID, id?}}`). The response returns the raw `token` string once — store it securely.
3. **Revoke** — `DeleteAuthorizationsID` (`DELETE /authorizations/{authID}`).

## Notes
- Prefer least-privilege tokens scoped to specific buckets over all-access tokens.
- In InfluxDB OSS 2.9+, tokens are hashed at rest. See `lifecycle/influxdata-lifecycle.yml`.
