# Salesforce Integrations

This folder intentionally has no `README.md`. It still appears as a valid
navigation section.

## JWT bearer flow

Store private keys outside the repository and inject secrets only at runtime.

```text
Client -> Signed assertion -> Token endpoint -> Access token -> REST API
```
