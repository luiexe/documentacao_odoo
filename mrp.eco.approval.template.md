# ECO Approval Template — `mrp.eco.approval.template`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `name` **(char)** — Role ⚠️ obrigatório
- `approval_type` **(selection)** — Approval Type ⚠️ obrigatório
  > Opções: `optional` (Approves, but the approval is optional), `mandatory` (Is required to approve), `comment` (Comments only)
- `user_ids` **(many2many)** — Users ⚠️ obrigatório → `res.users`
- `stage_id` **(many2one)** — Stage ⚠️ obrigatório → `mrp.eco.stage`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
