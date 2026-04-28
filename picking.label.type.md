# Choose whether to print product or lot/sn labels — `picking.label.type`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `label_type` **(selection)** — Labels to print ⚠️ obrigatório
  > Opções: `products` (Product Labels), `lots` (Lot/SN Labels)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `picking_ids` **(many2many)** — Picking → `stock.picking`
- `production_ids` **(many2many)** — Production → `mrp.production`
