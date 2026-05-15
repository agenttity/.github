# Agentity

| 🇬🇧 [English](README.md) | 🇫🇷 [Français](README.fr.md) |
|---|---|

**The identity layer for AI agents. — La couche d'identité des agents IA.**

---

## English

### The problem

AI agents are spreading across the internet — assistants, bots, autonomous workflows — without anyone being able to verify **who controls them**, **what they're allowed to do**, and **who is responsible** for their actions. Existing infrastructure (OAuth2, JWT, API keys) was designed for humans and static applications, not for autonomous, ephemeral software entities.

### The solution

An open source cryptographic identity protocol for AI agents, built on three fundamental questions:

1. **Who are you?** → Verifiable identity via Ed25519 key + self-signed DID  
2. **What are you allowed to do?** → Scopes validated against provider manifests  
3. **Who answers for your actions?** → Delegation chain rooted in a human verified via OIDC  

---

## Français

### Le problème

Les agents IA se multiplient sur Internet — assistants, bots, workflows autonomes — sans qu'il soit possible de savoir **qui les pilote**, **ce qu'ils ont le droit de faire**, et **qui est responsable** de leurs actions. Les infrastructures existantes (OAuth2, JWT, clés API) sont conçues pour des humains ou des applications statiques, pas pour des entités logicielles autonomes et éphémères.

### La solution

Un protocole open source d'identité cryptographique pour agents IA, basé sur trois questions fondamentales :

1. **Qui es-tu ?** → Identité vérifiable via clé Ed25519 + DID auto-signé  
2. **Qu'as-tu le droit de faire ?** → Scopes validés contre le manifeste du fournisseur  
3. **Qui répond de tes actes ?** → Chaîne de délégation remontant à un humain vérifié via OIDC  

---

[Monorepo](https://github.com/agenttity/agentity) · [npm](https://www.npmjs.com/package/@agentity/sdk) · [PyPI](https://pypi.org/project/agentity-sdk-python/) · [Apache 2.0](https://github.com/agenttity/agentity/blob/main/LICENSE)
