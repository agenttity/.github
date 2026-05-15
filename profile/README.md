![CI](https://github.com/agenttity/agentity/actions/workflows/ci.yml/badge.svg)
[![npm](https://img.shields.io/npm/v/@agentity/sdk)](https://www.npmjs.com/package/@agentity/sdk)
[![PyPI](https://img.shields.io/pypi/v/agentity-sdk-python)](https://pypi.org/project/agentity-sdk-python/)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://github.com/agenttity/agentity/blob/main/LICENSE)

# 🛡️ agenttity

**Open source cryptographic identity protocol for AI agents.**

Every AI agent receives a W3C-compatible DID (`did:agentity`), a signed Agent Identity Document (AID) with Ed25519 keys, and a scope system validated against service provider manifests — designed for LangChain, CrewAI, Vercel AI SDK, MCP, A2A, and any HTTP infrastructure.

---

## 📦 Core repository

| Package | Description |
|---------|-------------|
| [`agentity`](https://github.com/agenttity/agentity) | Monorepo — 11 packages, 3 languages (Rust, Python, TypeScript) |

### Identity & Crypto
- **Ed25519** keypairs, **W3C DID** (`did:agentity`), **base58 fingerprints**
- Self-signed **Agent Identity Document (AID)** with proof verification
- **Scope matching** with wildcards (`stripe:payments:*`)
- **Delegation chain** (max 10 levels) with cascade revocation

### SDKs
- **Python** → `pip install agentity-sdk-python` — LangChain, CrewAI, FastAPI
- **TypeScript** → `pnpm add @agentity/sdk` — Vercel AI SDK, Next.js, Node.js

### Security
- **OIDC** — Google, GitHub, Apple, Microsoft (verified owner DID)
- **Anti-replay** — UUID nonce + 5 min timestamp window
- **Rate limiting** — Redis per-DID with configurable limits
- **Key rotation** — `version+1` with `previousAid` link
- **Signed audit log** — HMAC-SHA256, verifiable via API

### Infrastructure
- **Registry** → FastAPI REST + WebSocket + PostgreSQL + Redis
- **Middleware** → FastAPI & Express (automatic token verification)
- **CLI** → `create`, `inspect`, `verify`, `sign`, `manifest`
- **Inspector** → Next.js dashboard with live revocations
- **MCP / A2A** → Protocol plugins for Anthropic & Google

---

## 🚀 Quick start

```python
from agentity_sdk import AgentKeyPair, RequestSigner

kp = AgentKeyPair()
aid = kp.create_identity("did:agentity:human:alice", ["stripe:payments:read"])

signer = RequestSigner(kp, aid)
headers = signer.sign_request("GET", "/api/v1/payments")
# → Agentity-Token, Agentity-Nonce, Agentity-Timestamp
```

```bash
# CLI
pip install agentity-sdk-python
python -m agentity_cli create --owner "did:agentity:human:alice" --scope "api:read"
```

## 📊 Test stats

| Language | Tests |
|----------|-------|
| Rust (core) | **17** ✅ |
| Python (SDK, registry, middleware, CLI, MCP, A2A) | **39** ✅ |
| TypeScript (SDK, middleware, manifest-gen) | **19** ✅ |
| **Total** | **74** ✅ |

---

## 📝 License

Apache 2.0 — see [agenttity/agentity](https://github.com/agenttity/agentity)
