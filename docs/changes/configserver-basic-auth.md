# Config server HTTP Basic auth (rejected)

## Proposed
- Add `spring-boot-starter-security`
- Require HTTP Basic credentials on config endpoints
- Source credentials from `CONFIG_USER` / `CONFIG_PASSWORD`

## Outcome
Closed without merge. Maintainers preferred securing the config server
with mTLS at the service-mesh layer rather than per-application basic
credentials. Tracking the mesh approach separately.
