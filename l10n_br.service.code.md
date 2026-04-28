# Product service codes defined by the city — `l10n_br.service.code`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `city_id` **(many2one)** — City ⚠️ obrigatório → `res.city`
  > The city this service code relates to.
- `code` **(char)** — Service Code ⚠️ obrigatório
  > The service code for this product as defined by the city.
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
  > The company for which this code applies.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
