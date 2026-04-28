# Product Forecast at Date — `mrp.product.forecast`

**Ordenação padrão:** `date`

---

## Campos Obrigatórios

- `production_schedule_id` **(many2one)** — Production Schedule ⚠️ obrigatório → `mrp.production.schedule`
- `date` **(date)** — Date ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `forecast_qty` **(float)** — Demand Forecast
- `replenish_qty` **(float)** — To Replenish
- `replenish_qty_updated` **(boolean)** — Replenish_qty has been manually updated
- `procurement_launched` **(boolean)** — Procurement has been run for this forecast
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
