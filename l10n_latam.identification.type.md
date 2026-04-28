# Identification Types — `l10n_latam.identification.type`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `description` **(char)** — Description
- `active` **(boolean)** — Active
- `is_vat` **(boolean)** — Is Vat
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `country_id` **(many2one)** — Country → `res.country`
