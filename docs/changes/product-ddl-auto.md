# Fix product-service ddl-auto

## Problem
`product-service.yaml` used `ddl-auto: create-drop`, which dropped and
recreated all tables on every restart, wiping product/inventory data.

## Fix
Changed to `ddl-auto: validate`. Hibernate now validates the existing
schema instead of recreating it.

## Follow-up
Schema changes should be managed by Flyway migrations, not Hibernate DDL.
