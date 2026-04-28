# Studio Approval Request — `studio.approval.request`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `mail_activity_id` **(many2one)** — Linked Activity ⚠️ obrigatório → `mail.activity`
- `rule_id` **(many2one)** — Approval Rule ⚠️ obrigatório → `studio.approval.rule`
- `res_id` **(many2one_reference)** — Record ID ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
