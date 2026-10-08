# Contributing

Thank you for wanting to help. This applies to every public repository sferarc publishes.

## Where things live

Libraries and tools, each released on its own:

| Repository | What it holds |
| --- | --- |
| `pgscram` | PostgreSQL SCRAM-SHA-256 verifiers in the on-disk format |
| `schemadigest` | A compact PostgreSQL schema description written for a model |
| `promptscan` | Detection of hostile content in text a language model will read |
| `auditchain` | A tamper-evident append-only hash chain with signed checkpoints |
| `ai-gateway-proxy` | A proxy handler for the Vercel AI Gateway |
| `vscode-ai-gateway` | A VS Code extension for Vercel AI Gateway models |
| `openapi` | TypeScript API clients generated from public OpenAPI specs |
| `rollup-plugin-import-cdn` | A Rollup plugin that resolves bare imports to CDN URLs |

PgBeam's SDKs and tooling:

| Repository | What it holds |
| --- | --- |
| `pgbeam-js` | The TypeScript SDK, published as `pgbeam` |
| `pgbeam-python` | The Python SDK, published to PyPI as `pgbeam` |
| `pgbeam-go` | The Go SDK, imported as `go.pgbeam.com/sdk` |
| `pgbeam-cli` | The `pgbeam` command line interface |
| `homebrew-pgbeam` | The Homebrew tap for the CLI |
| `pgbeam-openapi` | The public OpenAPI specification |
| `terraform-provider-pgbeam` | The Terraform provider |
| `pgbeam-crossplane` | The Crossplane provider |
| `pgbeam-pulumi` | The Pulumi provider |
| `pgbeam-docs` | The source of <https://pgbeam.com/docs> |
| `pgbeam-agent` | Agent skills, plugin and MCP manifests |
| `pgbeam-conformance` | Policy conformance vectors |

File issues and open pull requests on the repository that holds the code.

## Issues

An issue is the right place to start for a bug, a missing capability, a wrong doc page, or a conformance vector you disagree with.

A good issue says what you ran, what happened, what you expected, and which version you were on. For anything touching policy enforcement, include the exact SQL and the exact policy: those two decide the outcome, and a description of them usually does not. For a library, include the exact input, byte for byte where it matters, since most of these turn on bytes a paraphrase loses.

Do not report a suspected vulnerability in an issue. Follow [SECURITY.md](SECURITY.md) instead.

## Pull requests

- One change per pull request.
- A title that says what changed and why, not which files moved.
- Tests when the change is behavioural.
- Documentation updated in the same pull request when behaviour changes.
- No unrelated reformatting.

Each repository's README says how to build and test it. Run the formatter and linter it ships with rather than matching style by eye.

If you are planning something large, open an issue first and say what you have in mind. It is a cheap way to find out whether the design fits before you write it.

## Style

- Plain prose. No em dashes or en dashes; use commas, parentheses, or two sentences.
- Say what a thing does, not how significant it is.

## Licensing

Each repository carries its own licence: Apache-2.0 for PgBeam's SDKs and tooling and the Go libraries; MIT for `ai-gateway-proxy` and `vscode-ai-gateway`; ISC for `rollup-plugin-import-cdn` and for each client in `openapi`, as its `package.json` declares. By contributing you agree that your contribution is licensed under the licence of the repository you contribute to. There is no separate contributor licence agreement to sign.

## Getting help

See [SUPPORT.md](SUPPORT.md).
