# Approval Category Approver — `approval.category.approver`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `category_id` **(many2one)** — Approval Category ⚠️ obrigatório → `approval.category`
- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `required` **(boolean)** — Required
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `existing_user_ids` **(many2many)** — Existing User 🔒 readonly → `res.users`
