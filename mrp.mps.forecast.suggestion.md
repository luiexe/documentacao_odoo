# Forecast Demand Suggestion — `mrp.mps.forecast.suggestion`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `based_on` **(selection)** — Based on ⚠️ obrigatório
  > Opções: `actual_demand` (Actual Demand), `last_year` (Previous Year), `30_days` (Last 30 Days), `three_months` (Last 3 Months), `one_year` (Last 12 Months)
- `percent_factor` **(integer)** — Percent Factor ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `period` **(integer)** — Period
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `mrp_mps_id` **(many2one)** — Mrp Mps → `mrp.production.schedule`
- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`

## Campos Calculados (readonly)

- `based_on_readonly` **(char)** — Based On Readonly 🔒 readonly
- `quantity` **(float)** — Quantity 🔒 readonly
- `quantity_before_scale` **(float)** — Quantity Before Scale 🔒 readonly
