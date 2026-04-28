# Assign serial numbers to production order — `mrp.production.serials`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `lot_name` **(char)** — First SN
- `lot_quantity` **(integer)** — Number of SN
- `serial_numbers` **(text)** — Produced Serial Numbers
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `production_id` **(many2one)** — Production → `mrp.production`
- `workorder_id` **(many2one)** — Workorder → `mrp.workorder`
