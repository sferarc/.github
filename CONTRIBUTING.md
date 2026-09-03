# Contributing

Thank you for wanting to help.

## Where things live

| Repository           | What it holds                               |
| -------------------- | ------------------------------------------- |
| `pgbeam-js`          | The TypeScript SDK, published as `pgbeam`   |
| `pgbeam-go`          | The Go SDK, imported as `go.pgbeam.com/sdk` |
| `pgbeam-cli`         | The `pgbeam` command line interface         |
| `homebrew-pgbeam`    | The Homebrew tap for the CLI                |
| `pgbeam-openapi`     | The public OpenAPI specification            |
| `pgbeam-terraform`   | The Terraform provider                      |
| `pgbeam-crossplane`  | The Crossplane provider                     |
| `pgbeam-pulumi`      | The Pulumi provider                         |
| `pgbeam-docs`        | The source of <https://pgbeam.com/docs>     |
| `pgbeam-skills`      | Installable agent skills                    |
| `pgbeam-conformance` | Policy conformance vectors                  |

File issues and open pull requests on the repository that holds the code.

## Issues

An issue is the right place to start for a bug, a missing capability, a wrong
doc page, or a conformance vector you disagree with.

A good issue says what you ran, what happened, what you expected, and which
version you were on. For anything touching policy enforcement, include the
exact SQL and the exact policy: those two decide the outcome, and a description
of them usually does not.

Do not report a suspected vulnerability in an issue. Follow
[SECURITY.md](SECURITY.md) instead.

## Pull requests

- One change per pull request.
- A title that says what changed and why, not which files moved.
- Tests when the change is behavioural.
- Documentation updated in the same pull request when behaviour changes.
- No unrelated reformatting.

Each repository's README says how to build and test it. Run the formatter and
linter it ships with rather than matching style by eye.

If you are planning something large, open an issue first and say what you have
in mind. It is a cheap way to find out whether the design fits before you write
it.

## Style

- Plain prose. No em dashes or en dashes; use commas, parentheses, or two
  sentences.
- Say what a thing does, not how significant it is.

## Licensing

These repositories are Apache-2.0. By contributing you agree that your
contribution is licensed under the same terms, as set out in section 5 of the
licence. There is no separate contributor licence agreement to sign.

## Getting help

See [SUPPORT.md](SUPPORT.md).
