# ECO Approval — `mrp.eco.approval`

**Ordenação padrão:** `approval_date desc`

---

## Campos Obrigatórios

- `eco_id` **(many2one)** — ECO ⚠️ obrigatório → `mrp.eco`
- `approval_template_id` **(many2one)** — Template ⚠️ obrigatório → `mrp.eco.approval.template`
- `status` **(selection)** — Status ⚠️ obrigatório
  > Opções: `none` (Not Yet), `comment` (Commented), `approved` (Approved), `rejected` (Rejected)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `approval_date` **(datetime)** — Approval Date
- `is_closed` **(boolean)** — Is Closed
- `is_approved` **(boolean)** — Is Approved 🔒 readonly
- `is_rejected` **(boolean)** — Is Rejected 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — Approved by → `res.users`
- `required_user_ids` **(many2many)** — Requested Users → `res.users`
- `template_stage_id` **(many2one)** — Approval Stage 🔒 readonly → `mrp.eco.stage`
- `eco_stage_id` **(many2one)** — ECO Stage 🔒 readonly → `mrp.eco.stage`

## Campos Calculados (readonly)

- `name` **(char)** — Role 🔒 readonly
- `awaiting_my_validation` **(boolean)** — Awaiting My Validation 🔒 readonly
