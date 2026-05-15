# Agentity

**L'identité des agents IA.**

Les agents IA se multiplient sur Internet — assistants, bots, workflows autonomes — sans qu'il soit possible de savoir **qui les pilote**, **ce qu'ils ont le droit de faire**, et **qui est responsable** de leurs actions.

Agentity résout ça.

---

## Le problème

Aujourd'hui, un agent IA qui appelle une API n'a pas d'identité. Il peut mentir sur qui il est, ce qu'il a le droit de faire, ou rejouer une requête volée. Les infrastructures existantes (OAuth2, JWT, clés API) sont conçues pour des humains ou des applications statiques, pas pour des entités logicielles autonomes et éphémères.

## La solution

Un protocole open source d'identité cryptographique pour agents IA, basé sur trois questions fondamentales :

1. **Qui es-tu ?** → Identité vérifiable via clé Ed25519 + DID auto-signé
2. **Qu'as-tu le droit de faire ?** → Scopes validés contre le manifeste du fournisseur
3. **Qui répond de tes actes ?** → Chaîne de délégation remontant à un humain vérifié via OIDC

## Les principes

- **Sans infrastructure** : l'identité est auto-portée par le token — pas besoin de base de données centrale pour vérifier
- **Souverain** : le registre est auto-hébergeable (memory, PostgreSQL, Docker)
- **Compatible** : SDKs Python et TypeScript, middlewares FastAPI et Express, plugins MCP et A2A
- **Sécurisé** : anti-replay, rate limiting, rotation de clés, audit log signé, OIDC owner verification
- **Open source** : Apache 2.0, zéro vendor lock-in

---

[Le monorepo](https://github.com/agenttity/agentity) · [npm](https://www.npmjs.com/package/@agentity/sdk) · [PyPI](https://pypi.org/project/agentity-sdk-python/) · [Apache 2.0](https://github.com/agenttity/agentity/blob/main/LICENSE)
