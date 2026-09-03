# Security Policy

This policy covers everything Sfera Arc publishes. Today that is PgBeam, which
sits between AI agents and production databases, so a flaw in it is a flaw in
somebody's data boundary. We would rather hear about one from you than from an
incident.

## Reporting a vulnerability

Send the report to the address for the product it affects:

| Product | Where to send it    |
| ------- | ------------------- |
| PgBeam  | security@pgbeam.com |

If the repository has GitHub private vulnerability reporting enabled, the
Security tab works too and is preferred, because it keeps the whole exchange in
one place. If you are not sure which product a finding belongs to, pick any
address in that table and we will route it.

Please do not open a public issue, pull request, or discussion for a suspected
vulnerability, and please do not post it anywhere public until we have agreed a
disclosure date with you.

A report is easiest to act on when it contains:

- What you did, in enough detail that we can repeat it.
- What happened, and what you expected instead.
- The affected surface: a hostname, a package and version, a provider and
  version, or a commit.
- The impact you believe it has, and who it lands on.
- Any proof of concept, log excerpt, or capture. Redact real data before
  sending it.

Write in whatever language you are comfortable with. English gets the fastest
turnaround.

## What we commit to

- **Acknowledgement within 3 business days.** A human confirms receipt and
  gives you a reference.
- **A first assessment within 10 business days.** We tell you whether we
  reproduced it, how we rate its severity, and what we plan to do.
- **An update at least every 14 days** while the report is open, without you
  having to ask.
- **Credit, if you want it.** Tell us the name or handle to use, or tell us you
  would rather stay anonymous.
- **Coordinated disclosure.** We agree a date with you, publish an advisory on
  the affected repository, and name the fixed version.

We do not run a paid bug bounty. Saying so up front is fairer than letting you
find out after the work.

## Scope

Every public repository in this organization is in scope, as is every service
and package listed under a product below.

### PgBeam

- `pgbeam.com`, `api.pgbeam.com`, and the proxy endpoints under
  `proxy.pgbeam.app`.
- Published packages: the TypeScript SDK, the Go SDK, the CLI, and the
  OpenAPI package.
- The Terraform, Crossplane, and Pulumi providers.
- The agent gateway and its policy enforcement: read-only mode, table and
  column allowlists, row filters, PII masking, query budgets, the kill-switch,
  and the audit log. A construct that gets past any of those is exactly the
  class of bug we most want.

### Out of scope, whatever the product

- Findings against our vendors rather than us. Report those to the vendor.
- Missing security headers, cookie flags, or TLS configuration preferences with
  no demonstrated impact.
- Volumetric denial of service, load testing, and traffic flooding.
- Social engineering, phishing, or physical access against anyone connected
  with us.
- Scanner output with no working proof of concept.
- Reports that an unauthenticated endpoint returns data it is documented to
  return.

## Testing rules

Test against your own account and your own data. Do not access, modify, or
retain anyone else's. If a proof of concept needs more than your own account
can reach, stop and tell us what you would need; we would rather set you up
than have you improvise.

Do not degrade the service for other users, and do not run destructive
operations against shared infrastructure.

## Safe harbour

If you follow this policy in good faith, we will treat your research as
authorized, will not pursue or support legal action against you over it, and
will say so to anyone who asks. If a third party takes action over research
that stayed within this policy, tell us and we will make our position clear.

If you are unsure whether something is in bounds, ask first at the reporting
address for the product.

## Where else this is written down

PgBeam's security practices, which sit behind this policy, are described at
<https://pgbeam.com/security>.
