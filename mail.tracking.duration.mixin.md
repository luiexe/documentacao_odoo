# Mixin to compute the time a record has spent in each value a many2one field can take — `mail.tracking.duration.mixin`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly

## Campos Calculados (readonly)

- `duration_tracking` **(json)** — Status time 🔒 readonly
  > JSON that maps ids from a many2one field to seconds spent
- `rotting_days` **(integer)** — Days Rotting 🔒 readonly
  > Day count since this resource was last updated
- `is_rotting` **(boolean)** — Rotting 🔒 readonly
