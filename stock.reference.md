# Reference between stock documents — `stock.reference`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Reference ⚠️ obrigatório 🔒 readonly

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `move_ids` **(many2many)** — Stock Moves → `stock.move`
- `picking_ids` **(many2many)** — Transfers 🔒 readonly → `stock.picking`
- `production_ids` **(many2many)** — Productions → `mrp.production`
- `purchase_ids` **(many2many)** — Purchases → `purchase.order`
- `sale_ids` **(many2many)** — Sales → `sale.order`
