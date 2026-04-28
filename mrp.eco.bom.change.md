# ECO BoM changes — `mrp.eco.bom.change`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `change_type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `add` (Add), `remove` (Remove), `update` (Update)
- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `old_product_qty` **(float)** — Previous revision quantity
- `new_product_qty` **(float)** — New revision quantity
- `upd_product_qty` **(float)** — Quantity 🔒 readonly
- `conflict` **(boolean)** — Conflict
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `eco_id` **(many2one)** — Engineering Change → `mrp.eco`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `eco_rebase_id` **(many2one)** — ECO Rebase → `mrp.eco`
- `rebase_id` **(many2one)** — Rebase → `mrp.eco`
- `old_uom_id` **(many2one)** — Previous Product UoM → `uom.uom`
- `new_uom_id` **(many2one)** — New Product UoM → `uom.uom`
- `old_operation_id` **(many2one)** — Previous Consumed in Operation → `mrp.routing.workcenter`
- `new_operation_id` **(many2one)** — New Consumed in Operation → `mrp.routing.workcenter`
- `bom_line_id` **(many2one)** — BoM Line → `mrp.bom.line`
- `byproduct_id` **(many2one)** — BoM By-Product → `mrp.bom.byproduct`

## Campos Calculados (readonly)

- `uom_change` **(char)** — Unit 🔒 readonly
- `operation_change` **(char)** — Consumed in Operation 🔒 readonly
