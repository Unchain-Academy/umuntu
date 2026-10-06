# UMUNTU

**A local-first personal data foundation where every app and device needs your permission, and you can withdraw it at any time.**

> *Umuntu ngumuntu ngabantu* — "a person is a person through other people" (Nguni proverb).
> Your data starts with you, at home. You decide who else may use it.

**Status: design phase, no code yet (October 2026).** This repository is public from day one so that the design,
the threat model and the work can be followed and reviewed. Nothing here is ready to use.

---

## What UMUNTU will do

- Turn a device you already own — a laptop, a phone, or a small home box such as a Raspberry Pi — into a **personal data node**.
- Keep your notes, profiles and records **encrypted, on your device**, in open and portable formats (plain files: Markdown, JSON).
- Make every app, service or device that wants your data **hold a permission you issued**, limited to what it may read or write.
- Let you **withdraw** a permission in one action, and **read the log** of every access.
- **Sync** your own devices end-to-end encrypted, directly or through an optional relay that only sees encrypted data.
- Let you **share part of your data** with another person or a community node, under the same rules.

Identity uses **W3C Decentralized Identifiers (DIDs)**. Permissions use **W3C Verifiable Credentials**. Where possible we follow
the formats of the EU Digital Identity Wallet ecosystem (OpenID for Verifiable Credentials, SD-JWT) so the two can work together.

## What UMUNTU will not do

- No biometrics. No token. No central operator. Your own device is the root of trust.
- It cannot delete copies an app already made before you withdrew its permission. That is the app operator's legal duty
  (GDPR, right to erasure), and the access log tells you who had access.
- It is not an AI project. Software agents are just one more kind of app that must ask for permission.

## Planned work (subject to funding)

| | Milestone |
|---|---|
| M1 | Architecture, threat model, this repository |
| M2 | Core node: encrypted file store, folder import, DID identity, key backup and recovery |
| M3 | Permissions and sharing: issue, scope and withdraw credentials; access log |
| M4 | Encrypted sync across devices; optional, replaceable relay |
| M5 | Control panel (web), WCAG 2.2 AA, tested with non-technical people |
| M6 | Ready-to-flash Raspberry Pi image; install script for Debian-based mini-PCs |
| M7 | Open integration kit (API, client library, example app); first real integration |

See [ARCHITECTURE.md](ARCHITECTURE.md) for the design as it stands.

## Who is behind it

UMUNTU is started by **Unchain Academy** (M3 Vertex Performance Ltd, Malta), a learning company.
- **Victor Lardé** — founder, project lead. Not a developer. He built the company's learning-platform prototype alone,
  with an AI app builder, at the lowest possible cost; that prototype is proprietary and is **not** part of this repository.
- A team of three developers in Croatia and France, and a first outside beta-tester. Their names are added here as each one confirms.

Our learning platform will be the **second** user of UMUNTU, after an open example app anyone can copy.
UMUNTU does not depend on it and must work for any project.

## Licence

[Apache License 2.0](LICENSE). Everything in this repository — code, documentation, images — is released under it.

## Use of generative AI

We disclose it. See [GENAI.md](GENAI.md).

## Contact

info@unchainacademy.com
