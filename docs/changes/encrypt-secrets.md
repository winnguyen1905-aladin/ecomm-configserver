# Encrypt config secrets

## Why
JWT signing key and DB passwords were stored in plaintext in a public repo.

## What changed
- Config server now loads a symmetric `encrypt.key` from `ENCRYPT_KEY`
- Secrets stored as `{cipher}...` values, decrypted on serve
- `/encrypt` and `/decrypt` endpoints documented for generating values

## Action required
Rotate the previously leaked JWT secret and DB password before deploying.
