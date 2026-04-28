# Relation Model — `ir.model.relation`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Relation Name ⚠️ obrigatório
  > PostgreSQL table name implementing a many2many relation.
- `model` **(many2one)** — Model ⚠️ obrigatório → `ir.model`
- `module` **(many2one)** — Module ⚠️ obrigatório → `ir.module.module`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `write_date` **(datetime)** — Write Date
- `create_date` **(datetime)** — Create Date
