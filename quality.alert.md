# Quality Alert — `quality.alert`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `team_id` **(many2one)** — Team ⚠️ obrigatório → `quality.alert.team`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `email_cc` **(char)** — Email cc
- `name` **(char)** — Name
- `description` **(html)** — Description
- `date_assign` **(datetime)** — Date Assigned
- `date_close` **(datetime)** — Date Closed
- `action_corrective` **(html)** — Corrective Action
- `action_preventive` **(html)** — Preventive Action
- `priority` **(selection)** — Priority
  > Opções: `0` (Normal), `1` (Low), `2` (High), `3` (Very High)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `title` **(char)** — Title

## Relacionamentos

- `stage_id` **(many2one)** — Stage → `quality.alert.stage`
- `reason_id` **(many2one)** — Root Cause → `quality.reason`
- `tag_ids` **(many2many)** — Tags → `quality.tag`
- `picking_id` **(many2one)** — Picking → `stock.picking`
- `user_id` **(many2one)** — Responsible → `res.users`
- `partner_id` **(many2one)** — Vendor → `res.partner`
- `check_id` **(many2one)** — Check → `quality.check`
- `product_tmpl_id` **(many2one)** — Product → `product.template`
- `product_id` **(many2one)** — Product Variant → `product.product`
- `lot_ids` **(many2many)** — Lot → `stock.lot`
- `workorder_id` **(many2one)** — Operation → `mrp.workorder`
- `workcenter_id` **(many2one)** — Work Center → `mrp.workcenter`
- `production_id` **(many2one)** — Production Order → `mrp.production`
