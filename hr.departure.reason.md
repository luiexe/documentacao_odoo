# Departure Reason — `hr.departure.reason`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `name` **(char)** — Reason ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `country_id` **(many2one)** — Country → `res.country`

## Campos Calculados (readonly)

- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
