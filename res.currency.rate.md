# Currency Rate — `res.currency.rate`

**Ordenação padrão:** `name desc, id`

---

## Campos Obrigatórios

- `name` **(date)** — Date ⚠️ obrigatório
- `currency_id` **(many2one)** — Currency ⚠️ obrigatório 🔒 readonly → `res.currency`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `rate` **(float)** — Technical Rate
  > The rate of the currency to the currency of rate 1
- `company_rate` **(float)** — Company Rate
  > The currency of rate 1 to the rate of the currency.
- `inverse_company_rate` **(float)** — Inverse Company Rate
  > The rate of the currency to the currency of rate 1 
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
