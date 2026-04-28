# City — `res.city`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `country_id` **(many2one)** — Country ⚠️ obrigatório → `res.country`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `zipcode` **(char)** — Zip
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `state_id` **(many2one)** — State → `res.country.state`
- `l10n_br_zip_range_ids` **(one2many)** — Zip Ranges → `l10n_br.zip.range`
  > Brazil: technical field that maps a city to one or more zip code ranges.

## Campos Calculados (readonly)

- `l10n_br_zip_ranges` **(char)** — Frontend Zip Ranges 🔒 readonly
  > Brazil: technical field that maps a city to one or more zip code ranges for the frontend.
