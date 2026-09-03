# PgBeam

Safe Postgres access for AI agents.

PgBeam is a PostgreSQL proxy that enforces policy in the wire protocol, so an
agent gets a scoped credential instead of your database password. Read-only
mode, table and column allowlists, row filters, PII masking, query budgets, and
a kill-switch are decided before a statement reaches your database, and every
decision lands in a tamper-evident audit log. Connection pooling and query
caching come with it. No application changes.

- Documentation: <https://pgbeam.com/docs>
- Quickstart: <https://pgbeam.com/docs/quickstart>
- Security practices: <https://pgbeam.com/security>
- Status: <https://status.pgbeam.com>

## Repositories

| Repository                                                            | What it is                                   |
| --------------------------------------------------------------------- | -------------------------------------------- |
| [`pgbeam-js`](https://github.com/sferarc/pgbeam-js)                   | TypeScript SDK, published as `pgbeam`        |
| [`pgbeam-go`](https://github.com/sferarc/pgbeam-go)                   | Go SDK, imported as `go.pgbeam.com/sdk`      |
| [`pgbeam-cli`](https://github.com/sferarc/pgbeam-cli)                 | The `pgbeam` command line interface          |
| [`homebrew-pgbeam`](https://github.com/sferarc/homebrew-pgbeam)       | Homebrew tap for the CLI                     |
| [`pgbeam-openapi`](https://github.com/sferarc/pgbeam-openapi)         | Public OpenAPI specification                 |
| [`pgbeam-terraform`](https://github.com/sferarc/pgbeam-terraform)     | Terraform provider                           |
| [`pgbeam-crossplane`](https://github.com/sferarc/pgbeam-crossplane)   | Crossplane provider                          |
| [`pgbeam-pulumi`](https://github.com/sferarc/pgbeam-pulumi)           | Pulumi provider                              |
| [`pgbeam-docs`](https://github.com/sferarc/pgbeam-docs)               | Source of the documentation site             |
| [`pgbeam-skills`](https://github.com/sferarc/pgbeam-skills)           | Installable agent skills                     |
| [`pgbeam-conformance`](https://github.com/sferarc/pgbeam-conformance) | Policy conformance vectors, language neutral |

Issues and pull requests are welcome on all of them. See
[CONTRIBUTING.md](https://github.com/sferarc/.github/blob/main/CONTRIBUTING.md).
