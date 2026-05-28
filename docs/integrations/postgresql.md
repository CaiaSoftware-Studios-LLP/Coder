---
layout: page
title: PostgreSQL
permalink: /integrations/postgresql/
---

PostgreSQL connection info is passed as standard **libpq**-style variables and/or a single URL. The agent uses them when you ask for **terminal-based** work: `psql`, migration commands, app scripts, and similar.

## Example scenarios

- **Schema exploration** — Ask the agent to list tables, describe a schema, or explain relationships using `psql` meta-commands or SQL against a read-only user.
- **Write a migration** — Generate Alembic, Flyway, or raw SQL migrations from model changes in the repo; apply only after you review and approve destructive steps.
- **Seed or fixture data** — Ask for `INSERT` scripts or small datasets for local dev (watch for consent on DML).
- **Performance hints** — Paste `EXPLAIN ANALYZE` output and ask for index or query rewrites.
- **Data fix playbook** — Outline steps for a one-off update with backups and verification queries; let the agent format the SQL (execute only with explicit approval).
- **Connection debugging** — Diagnose SSL mode, host, port, and `pg_hba.conf`-style errors from connection error messages.

Prefer a **least-privilege** database user for everyday agent use; use the [local vault](../local-vault/) for passwords.

## Environment variables

You may set any of:

- `DATABASE_URL` or `CAIA_POSTGRES_URL`
- `CAIA_POSTGRES_HOST`, `CAIA_POSTGRES_PORT`, `CAIA_POSTGRES_USER`, `CAIA_POSTGRES_PASSWORD`, `CAIA_POSTGRES_DATABASE`, `CAIA_POSTGRES_SSLMODE`
- `PGHOST`, `PGPORT`, `PGUSER`, `PGPASSWORD`, `PGDATABASE`, `PGSSLMODE`

**Passwords** should usually live in the [local vault](../local-vault/) with bindings; keep Marketplace/UI fields empty so the server merges secrets per run.

## Safety

SQL **DML/DDL** and migration commands often trigger **destructive consent** in the main UI. Scheduler jobs need explicit destructive approval.

## Related

- [Marketplace](../marketplace/) — non-secret host/database fields.

[← All integrations](../integrations/)