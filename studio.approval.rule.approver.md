# Approval Rule Approvers Enriched — `studio.approval.rule.approver`

**Ordenação padrão:** `id desc`

---

## Campos Obrigatórios

- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`
- `rule_id` **(many2one)** — Rule ⚠️ obrigatório → `studio.approval.rule`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date_to` **(date)** — Date To
- `is_delegation` **(boolean)** — Is Delegation
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
