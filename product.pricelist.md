# Pricelist — `product.pricelist`

**Ordenação padrão:** `sequence, id, name`

---

## Campos Obrigatórios

- `name` **(char)** — Pricelist Name ⚠️ obrigatório
- `currency_id` **(many2one)** — Currency ⚠️ obrigatório → `res.currency`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
  > If unchecked, it will allow you to hide the pricelist without removing it.
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `code` **(char)** — E-commerce Promotional Code
- `selectable` **(boolean)** — Selectable
  > Allow the end user to choose this price list

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `country_group_ids` **(many2many)** — Country Groups → `res.country.group`
- `item_ids` **(one2many)** — Pricelist Rules → `product.pricelist.item`
- `website_id` **(many2one)** — Website → `website`
  > If you want a pricelist to be available on a website,you must fill in this field or make it selectable.Otherwise, the pricelist will not apply to any website.
