# Shared default config profile

Extracted common settings (RabbitMQ, Redis, multipart) into a shared
`application.yaml` served by the config server.

## Why
- RabbitMQ/Redis/multipart blocks were duplicated across service files
- The duplicated blocks had already drifted (ddl-auto differed)

## What changed
- New `application.yaml` holds common properties (default profile)
- `gateway-service.yaml` / `product-service.yaml` keep only overrides
- Client effective config is the merge of default + service file
