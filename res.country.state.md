# Country state — `res.country.state`

**Ordenação padrão:** `code, id`

---

## Campos Obrigatórios

- `country_id` **(many2one)** — Country ⚠️ obrigatório → `res.country`
- `name` **(char)** — State Name ⚠️ obrigatório
  > Administrative divisions of a country. E.g. Fed. State, Department, Canton
- `code` **(char)** — State Code ⚠️ obrigatório
  > The state code.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
