# Sequence Date Range — `ir.sequence.date_range`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `date_from` **(date)** — From ⚠️ obrigatório
- `date_to` **(date)** — To ⚠️ obrigatório
- `sequence_id` **(many2one)** — Main Sequence ⚠️ obrigatório → `ir.sequence`
- `number_next` **(integer)** — Next Number ⚠️ obrigatório
  > Next number of this sequence

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `number_next_actual` **(integer)** — Actual Next Number
  > Next number that will be used. This number can be incremented frequently so the displayed value might already be obsolete
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
