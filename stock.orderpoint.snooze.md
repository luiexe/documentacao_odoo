# Snooze Orderpoint — `stock.orderpoint.snooze`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `predefined_date` **(selection)** — Snooze for
  > Opções: `day` (1 Day), `week` (1 Week), `month` (1 Month), `custom` (Custom)
- `snoozed_until` **(date)** — Snooze Date
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `orderpoint_ids` **(many2many)** — Orderpoint → `stock.warehouse.orderpoint`
