# Recycling Record — `data_recycle.record`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `res_id` **(integer)** — Record ID
- `res_model_name` **(char)** — Model Name 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `recycle_model_id` **(many2one)** — Recycle Model → `data_recycle.model`
- `res_model_id` **(many2one)** — Model 🔒 readonly → `ir.model`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`

## Campos Calculados (readonly)

- `name` **(char)** — Record Name 🔒 readonly
