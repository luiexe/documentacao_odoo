# Wizard to Split Multiple Productions — `mrp.production.split.multi`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `production_ids` **(one2many)** — Productions To Split → `mrp.production.split`
