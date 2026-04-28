# Approval Rule Delegate — `studio.approval.rule.delegate`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `approval_rule_id` **(many2one)** — Approval Rule ⚠️ obrigatório → `studio.approval.rule`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date_to` **(date)** — Until
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `approver_ids` **(many2many)** — Approvers → `res.users`
- `users_to_notify` **(many2many)** — Notify to → `res.users`
