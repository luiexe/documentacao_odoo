# Stock Package Destination — `stock.package.destination`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `move_line_ids` **(many2many)** — Move Line ⚠️ obrigatório → `stock.move.line`
- `location_dest_id` **(many2one)** — Destination location ⚠️ obrigatório → `stock.location`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `filtered_location` **(one2many)** — Filtered Location 🔒 readonly → `stock.location`
