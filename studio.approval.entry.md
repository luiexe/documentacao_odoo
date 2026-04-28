# Studio Approval Entry — `studio.approval.entry`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `user_id` **(many2one)** — Approved/rejected by ⚠️ obrigatório → `res.users`
- `rule_id` **(many2one)** — Approval Rule ⚠️ obrigatório → `studio.approval.rule`
- `res_id` **(many2one_reference)** — Record ID ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name 🔒 readonly
- `model` **(char)** — Model Name 🔒 readonly
- `method` **(char)** — Method 🔒 readonly
- `approved` **(boolean)** — Approved
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `action_id` **(many2one)** — Action 🔒 readonly → `ir.actions.actions`

## Campos Calculados (readonly)

- `reference` **(char)** — Reference 🔒 readonly
