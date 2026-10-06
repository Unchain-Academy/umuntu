# UMUNTU — architecture (draft 0.1, October 2026)

Status: a design draft written before any code. It will be replaced by the M1 deliverable.

## Parts

```
 your devices                                    others
 ┌──────────────────────────────┐
 │  UMUNTU node                 │   permission    ┌─────────────┐
 │  ┌──────────┐  ┌───────────┐ │ ◄────────────── │ app / device│
 │  │ encrypted│  │ permission│ │   (credential)  └─────────────┘
 │  │ file     │◄─┤ gate      │ │                 ┌─────────────┐
 │  │ store    │  │ + access  │ │ ◄────────────── │ person or   │
 │  └──────────┘  │ log       │ │   (credential)  │ community   │
 │       ▲        └───────────┘ │                 │ node        │
 │       │ sync (end-to-end encrypted)            └─────────────┘
 │  ┌────┴─────┐                │
 │  │ owner    │  DID + keys    │      optional relay: sees only ciphertext,
 │  │ identity │                │      self-hostable, replaceable
 │  └──────────┘                │
 └──────────────────────────────┘
```

1. **Owner identity.** A DID (did:key or did:peer) whose keys live on the owner's devices. Key backup and recovery
   without a central party (recovery phrase, second device, or trusted contacts — to be decided in M1/M2).
2. **Encrypted file store.** Plain files (Markdown, JSON) encrypted at rest. An existing folder can be imported.
3. **Permission gate.** Every read or write must present a Verifiable Credential issued by the owner, stating
   who, which data, which actions, until when. Permissions expire by default unless the owner renews them.
   Checked on every request.
4. **Access log.** Append-only, readable and exportable by the owner.
5. **Sync.** End-to-end encrypted between the owner's devices, directly on the local network or through an
   optional relay. An existing sync library will be evaluated before writing our own.
6. **Sharing.** The same credentials, issued to another person or a community node, for a chosen subset of data.
7. **Integration kit.** A small documented API and client library, with an open example app.

## Threat model (to be written in M1)

Lost or stolen device · malicious or over-curious app · compromised relay · revoked app keeping old copies ·
owner losing all keys.

## Standards we expect to use

W3C DID Core · W3C Verifiable Credentials Data Model · OpenID for Verifiable Credentials and SD-JWT where they
help interoperability with EU Digital Identity Wallets · WCAG 2.2 AA for the control panel.
