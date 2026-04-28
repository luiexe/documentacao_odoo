# Fiscal Year — `account.fiscal.year`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `date_from` **(date)** — Start Date ⚠️ obrigatório
  > Start Date, included in the fiscal year.
- `date_to` **(date)** — End Date ⚠️ obrigatório
  > Ending Date, included in the fiscal year.
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
