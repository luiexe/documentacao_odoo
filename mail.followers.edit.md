# Followers edit wizard — `mail.followers.edit`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `res_model` **(char)** — Related Document Model ⚠️ obrigatório
  > Model of the followed resource
- `operation` **(selection)** — Operation ⚠️ obrigatório
  > Opções: `add` (Add), `remove` (Remove)
- `partner_ids` **(many2many)** — Followers ⚠️ obrigatório → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `res_ids` **(char)** — Related Document IDs
  > Ids of the followed resources
- `message` **(html)** — Message
- `notify` **(boolean)** — Notify Recipients
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
