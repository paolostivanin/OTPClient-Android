# Security Policy

This app stores one-time-password secrets, so security reports are taken seriously.

## Reporting a vulnerability

Please **do not** open a public issue. Report privately through GitHub's
["Report a vulnerability"](../../security/advisories/new) form on this repository.

Include the affected version/commit, a description of the issue, and steps to
reproduce. You can expect an initial response within a few days.

## Scope

Of particular interest: the database format and key derivation (`core-crypto`,
`core-database`), import/export parsers (`core-importexport`), sync providers
(`core-sync`), and anything that could leak secrets (logs, backups, screenshots,
clipboard, intents).
