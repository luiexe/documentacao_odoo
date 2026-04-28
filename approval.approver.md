# Approver — `approval.approver`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `status` **(selection)** — Status 🔒 readonly
  > Opções: `new` (New), `pending` (To Approve), `waiting` (Waiting), `approved` (Approved), `refused` (Refused), `cancel` (Cancel)
- `required` **(boolean)** — Required 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `existing_request_user_ids` **(many2many)** — Existing Request User 🔒 readonly → `res.users`
- `request_id` **(many2one)** — Request → `approval.request`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`

## Campos Calculados (readonly)

- `category_approver` **(boolean)** — Category Approver 🔒 readonly
- `can_edit` **(boolean)** — Can Edit 🔒 readonly
- `can_edit_user_id` **(boolean)** — Can Edit User 🔒 readonly
  > Simple users should not be able to remove themselves as approvers because they will lose access to the record if they misclick.
