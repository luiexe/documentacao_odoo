# Bank — `res.bank`

**Ordenação padrão:** `name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `street` **(char)** — Street
- `street2` **(char)** — Street2
- `zip` **(char)** — Zip
- `city` **(char)** — City
- `email` **(char)** — Email
- `phone` **(char)** — Phone
- `active` **(boolean)** — Active
- `bic` **(char)** — Bank Identifier Code
  > Sometimes called BIC or Swift.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `state` **(many2one)** — Fed. State → `res.country.state`
- `country` **(many2one)** — Country → `res.country`

## Campos Calculados (readonly)

- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
