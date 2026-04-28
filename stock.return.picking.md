# Return Picking — `stock.return.picking`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `picking_id` **(many2one)** — Picking → `stock.picking`
- `product_return_moves` **(one2many)** — Moves → `stock.return.picking.line`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`

## Campos Calculados (readonly)

- `picking_type_code` **(selection)** — Type of Operation 🔒 readonly
  > Opções: `incoming` (Receipt), `outgoing` (Delivery), `internal` (Internal Transfer), `mrp_operation` (Manufacturing)
