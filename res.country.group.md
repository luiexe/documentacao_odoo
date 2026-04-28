# Country Group — `res.country.group`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `code` **(char)** — Code
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `country_ids` **(many2many)** — Countries → `res.country`
- `pricelist_ids` **(many2many)** — Pricelists → `product.pricelist`
- `exclude_state_ids` **(many2many)** — Fiscal Exceptions → `res.country.state`
  > Those states are ignored by the fiscal positions
