# sferarc

sferarc builds Postgres tools for developers and a few products for everyone else. Each product has its own site; the open source libraries below are released on their own and need nothing else from this organization.

[sferarc.com](https://sferarc.com) · [Contributing](https://github.com/sferarc/.github/blob/main/CONTRIBUTING.md) · [Security](https://github.com/sferarc/.github/blob/main/SECURITY.md) · [Support](https://github.com/sferarc/.github/blob/main/SUPPORT.md)

## Products

| Product | What it does | Status |
| --- | --- | --- |
| [PgBeam](https://pgbeam.com) | A Postgres proxy that gives AI agents scoped credentials and enforces policy in the wire protocol: read-only mode, table and column allowlists, row filters, PII masking, query budgets, a kill switch and a tamper-evident audit log. Works with any Postgres host. | Live |
| pgseek | Full-text search inside Postgres, served from a native index with BM25 ranking. | In development |
| [Nuclom](https://nuclom.com) | One knowledge hub over Slack, Notion, GitHub and meeting recordings that answers questions with sources. | Private beta |
| [Photocall](https://photocall.sferadev.com) | A photo booth kiosk for weddings, parties and company events, with QR pickup and on-site printing. | Live |
| [Aula](https://aula.sferarc.com) | A teaching site of their own for independent teachers and small schools. | Early access |
| Seating | A seating planner for weddings and events. | Coming soon |

## Open source

### Postgres

| Repository | What it does | Install | License |
| --- | --- | --- | --- |
| [pgscram](https://github.com/sferarc/pgscram) | Produce and read PostgreSQL's stored SCRAM-SHA-256 verifier, so a password never has to reach the server. No dependencies. | `go get github.com/sferarc/pgscram` | Apache-2.0 |
| [schemadigest](https://github.com/sferarc/schemadigest) | Read a PostgreSQL catalog and reduce it to a compact schema summary for a language model's context. | `go get github.com/sferarc/schemadigest` | Apache-2.0 |
| [pgbeam-conformance](https://github.com/sferarc/pgbeam-conformance) | Language-neutral test vectors for wire-level Postgres policy enforcement: a policy, a statement and the expected decision. | Clone the repository | Apache-2.0 |

### AI and agents

| Repository | What it does | Install | License |
| --- | --- | --- | --- |
| [promptscan](https://github.com/sferarc/promptscan) | Detect hostile content aimed at a language model in untrusted text: bidi overrides, mixed-script words and Unicode tag-block smuggling. | `go get github.com/sferarc/promptscan` | Apache-2.0 |
| [peeksafe](https://github.com/sferarc/peeksafe) | Statistically valid gates for non-deterministic eval suites: stop a run early without losing error control. | Not on npm yet | Apache-2.0 |
| [ai-gateway-proxy](https://github.com/sferarc/ai-gateway-proxy) | A proxy handler for the Vercel AI Gateway with request and response hooks and streaming, for Next.js, Hono and Express. | `npm install ai-gateway-proxy` | MIT |
| [vscode-ai-gateway](https://github.com/sferarc/vscode-ai-gateway) | A VS Code extension that brings Vercel AI Gateway models to the editor's chat. | [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=SferaDev.vscode-extension-vercel-ai) | MIT |

### Integrity

| Repository | What it does | Install | License |
| --- | --- | --- | --- |
| [auditchain](https://github.com/sferarc/auditchain) | Tamper-evident append-only logs for Go, with optional signed checkpoints. | `go get github.com/sferarc/auditchain` | Apache-2.0 |

### API clients and build tooling

| Repository | What it does | Install | License |
| --- | --- | --- | --- |
| [openapi](https://github.com/sferarc/openapi) | Type-safe TypeScript clients generated from public OpenAPI specs, listed at [openapi.sferadev.com](https://openapi.sferadev.com). Published: `vercel-api-js`, `cloudflare-api-js`, `netlify-api`, `keycloak-api`, `litellm-api`, `nuki-api-js`, `v0-api`, `zoom-api-js`. | `npm install vercel-api-js` (or any client above) | ISC, per package |
| [rollup-plugin-import-cdn](https://github.com/sferarc/rollup-plugin-import-cdn) | A Rollup plugin that resolves bare imports to CDN URLs. | `npm install rollup-plugin-import-cdn` | ISC |

### PgBeam SDKs and tools

The PgBeam proxy and control plane are developed privately. These are the published parts, all Apache-2.0.

| Repository | What it is | Install |
| --- | --- | --- |
| [pgbeam-js](https://github.com/sferarc/pgbeam-js) | TypeScript SDK | `npm install pgbeam` |
| [pgbeam-python](https://github.com/sferarc/pgbeam-python) | Python SDK, blocking and asyncio | `pip install pgbeam` |
| [pgbeam-go](https://github.com/sferarc/pgbeam-go) | Go SDK | `go get go.pgbeam.com/sdk` |
| [pgbeam-cli](https://github.com/sferarc/pgbeam-cli) | The `pgbeam` command line interface | `npm install -g @pgbeam/cli` |
| [homebrew-pgbeam](https://github.com/sferarc/homebrew-pgbeam) | Homebrew tap for the CLI's native binary | `brew install sferarc/pgbeam/pgbeam` |
| [pgbeam-openapi](https://github.com/sferarc/pgbeam-openapi) | The public OpenAPI contract | `npm install @pgbeam/openapi` |
| [pgbeam-pulumi](https://github.com/sferarc/pgbeam-pulumi) | Pulumi provider | `npm install @pgbeam/pulumi` |
| [terraform-provider-pgbeam](https://github.com/sferarc/terraform-provider-pgbeam) | Terraform provider | [GitHub releases](https://github.com/sferarc/terraform-provider-pgbeam/releases) |
| [pgbeam-crossplane](https://github.com/sferarc/pgbeam-crossplane) | Crossplane provider, as Kubernetes custom resources | `ghcr.io/sferarc/provider-pgbeam` |
| [pgbeam-agent](https://github.com/sferarc/pgbeam-agent) | Agent skills, the Agent Plugin and MCP manifests, and `AGENTS.md` instructions | Clone the repository |
| [pgbeam-docs](https://github.com/sferarc/pgbeam-docs) | Source of [pgbeam.com/docs](https://pgbeam.com/docs) | |

## Contributing and security

Issues and pull requests are welcome on every public repository. [CONTRIBUTING.md](https://github.com/sferarc/.github/blob/main/CONTRIBUTING.md) says where things live and what a good issue or pull request looks like.

Report a suspected vulnerability privately, never in a public issue: use the Security tab of the affected repository, or follow [SECURITY.md](https://github.com/sferarc/.github/blob/main/SECURITY.md).
