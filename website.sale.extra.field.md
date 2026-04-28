# E-Commerce Extra Info Shown on product page — `website.sale.extra.field`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `field_id` **(many2one)** — Field ⚠️ obrigatório → `ir.model.fields`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `website_id` **(many2one)** — Website → `website`

## Campos Calculados (readonly)

- `label` **(char)** — Field Label 🔒 readonly
- `name` **(char)** — Field Name 🔒 readonly
