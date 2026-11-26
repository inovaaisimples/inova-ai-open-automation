# Security Policy

## Supported content

Security fixes are applied to the default branch for maintained examples and templates.

## Reporting a vulnerability

Do **not** open a public issue for a suspected vulnerability. Contact the maintainers through the private security-reporting channel available on GitHub for this repository. Include reproduction steps, impact, and a minimal redacted proof of concept. Do not include secrets or personal data.

We aim to acknowledge reports within 7 business days and will coordinate disclosure after remediation.

## Secure-use baseline

- Store credentials only in n8n credentials or an approved secret manager.
- Use least-privilege API tokens and rotate exposed credentials immediately.
- Review imported workflows before activation and restrict public webhooks with authentication in production.
