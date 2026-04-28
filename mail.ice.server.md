# ICE Server — `mail.ice.server`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `server_type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `stun` (stun:), `turn` (turn:)
- `uri` **(char)** — URI ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `username` **(char)** — Username
- `credential` **(char)** — Credential
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
