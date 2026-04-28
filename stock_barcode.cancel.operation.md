# Cancel Operation — `stock_barcode.cancel.operation`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `picking_id` **(many2one)** — Transfer 🔒 readonly → `stock.picking`

## Campos Calculados (readonly)

- `picking_name` **(char)** — Transfer Name 🔒 readonly
