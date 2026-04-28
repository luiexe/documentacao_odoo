# Wizard in case of consumption in warning/strict and more component has been used for a MO (related to the bom) — `mrp.consumption.warning`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `mrp_production_ids` **(many2many)** — Mrp Production → `mrp.production`
- `mrp_consumption_warning_line_ids` **(one2many)** — Mrp Consumption Warning Line → `mrp.consumption.warning.line`

## Campos Calculados (readonly)

- `mrp_production_count` **(integer)** — Mrp Production Count 🔒 readonly
- `consumption` **(selection)** — Consumption 🔒 readonly
  > Opções: `flexible` (Allowed), `warning` (Allowed with warning), `strict` (Blocked)
