# Vantys

Execution authority for AI-initiated commerce.

Vantys is a server-side authorization and enforcement layer that determines whether an AI-initiated action is allowed to execute before irreversible operations occur.

---

## Overview

AI agents can initiate purchases, reservations, and other actions that have real-world consequences.

Once execution becomes asynchronous, distributed, or retried, UI-based approval and agent-side rules are no longer enforceable. In these conditions, actions can bypass intended approval paths and execute without explicit authorization.

Vantys introduces a deterministic execution gate between AI intent and platform execution.

---

## What Vantys does

For every AI-initiated action, Vantys:

- Accepts a strictly defined execution intent
- Validates intent against authoritative state
- Evaluates authorization deterministically
- Returns an explicit **ALLOW** or **BLOCK** decision
- Issues a single-use execution token on approval

Enforcement occurs at the platform execution boundary. Actions without a valid execution token are rejected.

---

## What Vantys does not do

Vantys is intentionally narrow in scope.

- We do not build agent interfaces or UIs
- We do not orchestrate workflows
- We do not index catalogs or perform discovery
- We do not process payments
- We do not replace commerce platforms or payment providers

Vantys exists solely to authorize execution.

---

## Supported platforms

- Shopify (v1)

Additional platforms may be supported based on demand.

---

## Status

In use with agencies integrating AI-initiated commerce flows.

---

License: Apache 2.0
