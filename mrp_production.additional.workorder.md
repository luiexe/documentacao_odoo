# Additional Workorder — `mrp_production.additional.workorder`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `production_id` **(many2one)** — Production ⚠️ obrigatório → `mrp.production`
- `name` **(char)** — Title ⚠️ obrigatório
- `workcenter_id` **(many2one)** — Work Center ⚠️ obrigatório → `mrp.workcenter`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `duration_expected` **(float)** — Expected Duration
- `date_start` **(datetime)** — Date Start
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `blocked_by_workorder_id` **(many2one)** — Insert after operation → `mrp.workorder`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `employee_assigned_ids` **(many2many)** — Employee → `hr.employee`
