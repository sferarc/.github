# Sferarc

Sferarc builds developer infrastructure for PostgreSQL and for the AI agents that talk to it. Several separate projects live here: PgBeam, the largest, is a hosted proxy with its own family of clients and providers, and alongside it are standalone Go libraries and a language-neutral test corpus, each usable on its own with nothing from PgBeam installed.

Everything published here is Apache-2.0.

## Standalone Go libraries

Independent packages. Each solves one problem and is released on its own, so you can use it with nothing else from this organization installed.

### [pgscram](https://github.com/sferarc/pgscram)

`go get github.com/sferarc/pgscram` — produce and read PostgreSQL's stored SCRAM-SHA-256 verifier, the `SCRAM-SHA-256$<iterations>:<salt>$<StoredKey>:<ServerKey>` string that lives in `pg_authid.rolpassword`. Derive one from a password, hand it straight to `CREATE ROLE ... PASSWORD`, and the plaintext never reaches the server. For anyone who issues or holds Postgres credentials: a pooler, a wire-protocol proxy, a control plane that provisions roles, a migration moving credentials between systems. Developed for and used in production by PgBeam, which mints verifiers without ever holding the passwords they stand for. It is deliberately *not* a SCRAM authentication implementation — it is the on-disk format only, and composes with [xdg-go/scram](https://github.com/xdg-go/scram) for the RFC 5802 exchange. No dependencies outside the standard library; requires Go 1.24 for `crypto/pbkdf2`.

### [schemadigest](https://github.com/sferarc/schemadigest)

`go get github.com/sferarc/schemadigest` — read a PostgreSQL catalog over a `pgx` connection and reduce it to a compact JSON summary for a language model's context: qualified table names, approximate row counts from `pg_class.reltuples`, comments, primary keys, foreign keys rendered as `col -> ref_table(ref_col)`, and per column only name, type and a masked flag. Two halves that are usable separately: `Read` is a plain catalog reader over four catalog queries, and `From` is the opinionated reduction. For text-to-SQL and agent tooling that would otherwise ship a `pg_dump --schema-only` into the prompt.

### [auditchain](https://github.com/sferarc/auditchain)

`go get github.com/sferarc/auditchain` — tamper-evident append-only logs. Records are hashed into a chain, keyed with an HMAC, so editing a record, deleting from the middle, rehashing the tail, or continuing past a truncation are all detectable by an offline walk of the stored rows. The threat model is stated plainly in the README, including the one attack a hash chain cannot catch on its own (truncating the tail and stopping) and the `anchor` subpackage of Merkle checkpoints that closes it. The core package has no dependencies outside the standard library; `anchor` is the only thing that pulls in [transparency-dev](https://github.com/transparency-dev), and only if you import it.

## Conformance vectors

### [pgbeam-conformance](https://github.com/sferarc/pgbeam-conformance)

A language-neutral corpus of `(policy, statement) -> expected decision` cases for wire-level Postgres policy enforcement — 44 cases across 10 profiles, covering read-only mode, statement allowlists, fail-closed input handling, relation allow/deny matching, column masking, row filters, lock-taking DDL, and bounded write counts. For anyone building a proxy, an MCP server, or a driver shim that stands between an agent and a database and wants "the policy is enforced" to be a checkable claim rather than a marketing one. The vectors are generated from PgBeam's policy engine and are published as one implementation's answers, not as a standard; running them against something else and publishing the diff is the intended use.

## PgBeam

Safe Postgres access for AI agents: <https://pgbeam.com>

PgBeam is a globally distributed PostgreSQL proxy that enforces policy in the wire protocol, so an agent gets a scoped credential instead of your database password. Read-only mode, table and column allowlists, row filters, PII masking, query budgets, and a kill-switch are decided before a statement reaches your database, and every decision lands in a tamper-evident audit log. Connection pooling and query caching come with it. It works with any Postgres host and needs no application changes — swap the connection string, or point the agent at the hosted MCP endpoint. Using it needs an account.

- Documentation: <https://pgbeam.com/docs>
- Quickstart: <https://pgbeam.com/docs/quickstart>
- Security practices: <https://pgbeam.com/security>
- Status: <https://status.pgbeam.com>

The proxy and control plane are developed in a private monorepo. These are the published parts:

| Repository | What it is |
| --- | --- |
| [`pgbeam-agent`](https://github.com/sferarc/pgbeam-agent) | Everything an agent needs to connect: installable agent skills, `AGENTS.md` operating instructions, and the Agent Plugin and MCP manifests |
| [`pgbeam-cli`](https://github.com/sferarc/pgbeam-cli) | The `pgbeam` command line interface, on npm as `@pgbeam/cli` |
| [`homebrew-pgbeam`](https://github.com/sferarc/homebrew-pgbeam) | Homebrew tap for the CLI's native binary: `brew install sferarc/pgbeam/pgbeam` |
| [`pgbeam-js`](https://github.com/sferarc/pgbeam-js) | TypeScript SDK for the API, on npm as `pgbeam` |
| [`pgbeam-go`](https://github.com/sferarc/pgbeam-go) | Go SDK for the API, imported as `go.pgbeam.com/sdk` |
| [`pgbeam-openapi`](https://github.com/sferarc/pgbeam-openapi) | The public OpenAPI contract, bundled and separated, on npm as `@pgbeam/openapi` |
| [`pgbeam-terraform`](https://github.com/sferarc/pgbeam-terraform) | Terraform provider |
| [`pgbeam-pulumi`](https://github.com/sferarc/pgbeam-pulumi) | Pulumi provider |
| [`pgbeam-crossplane`](https://github.com/sferarc/pgbeam-crossplane) | Crossplane provider, Kubernetes custom resources |
| [`pgbeam-docs`](https://github.com/sferarc/pgbeam-docs) | Source of <https://pgbeam.com/docs> |

## Contributing

Issues and pull requests are welcome on every repository above. See [CONTRIBUTING.md](https://github.com/sferarc/.github/blob/main/CONTRIBUTING.md), and [SECURITY.md](https://github.com/sferarc/.github/blob/main/SECURITY.md) for reporting a vulnerability privately rather than in a public issue.
