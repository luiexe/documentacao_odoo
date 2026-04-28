# Work Location — `hr.work.location`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `name` **(char)** — Work Location ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `location_type` **(selection)** — Cover Image ⚠️ obrigatório
  > Opções: `home` (Home), `office` (Office), `other` (Other)
- `address_id` **(many2one)** — Work Address ⚠️ obrigatório → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `location_number` **(char)** — Location Number
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
