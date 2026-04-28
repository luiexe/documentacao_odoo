# Incoterms — `account.incoterms`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
  > Incoterms are series of sales terms. They are used to divide transaction costs and responsibilities between buyer and seller and reflect state-of-the-art transportation practices.
- `code` **(char)** — Code ⚠️ obrigatório
  > Incoterm Standard Code

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
  > By unchecking the active field, you may hide an INCOTERM you will not use.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
