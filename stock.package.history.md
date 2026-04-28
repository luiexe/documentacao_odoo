# Stock Package History — `stock.package.history`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `move_line_ids` **(one2many)** — Move Lines ⚠️ obrigatório → `stock.move.line`
- `package_id` **(many2one)** — Package ⚠️ obrigatório → `stock.package`
- `package_name` **(char)** — Package Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `parent_orig_name` **(char)** — Origin Container Name
- `parent_dest_name` **(char)** — Destination Container Name
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `location_id` **(many2one)** — Origin Location → `stock.location`
- `location_dest_id` **(many2one)** — Destination Location → `stock.location`
- `package_type_id` **(many2one)** — Package Type 🔒 readonly → `stock.package.type`
- `parent_orig_id` **(many2one)** — Origin Container → `stock.package`
- `parent_dest_id` **(many2one)** — Destination Container → `stock.package`
- `outermost_dest_id` **(many2one)** — Outermost Destination Container → `stock.package`
- `picking_ids` **(many2many)** — Transfers → `stock.picking`
