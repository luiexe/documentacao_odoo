# Eco Routing changes — `mrp.eco.routing.change`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `eco_id` **(many2one)** — Engineering Change ⚠️ obrigatório → `mrp.eco`
- `change_type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `add` (Add), `remove` (Remove), `update` (Update)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `upd_time_mode` **(char)** — Mode Change
- `upd_time_mode_batch` **(integer)** — Batch count Change
- `upd_time_cycle_manual` **(float)** — Manual Duration Change
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `workcenter_id` **(many2one)** — Work Center → `mrp.workcenter`
- `operation_id` **(many2one)** — Operation Id → `mrp.routing.workcenter`
- `quality_point_id` **(many2one)** — Quality Point → `quality.point`
- `test_type` **(many2one)** — Step Type 🔒 readonly → `quality.point.test_type`
  > Defines the type of the quality control point.

## Campos Calculados (readonly)

- `operation_name` **(char)** — Operation 🔒 readonly
- `step` **(char)** — Step 🔒 readonly
- `title` **(char)** — Title 🔒 readonly
