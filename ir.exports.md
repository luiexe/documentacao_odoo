# Exports — `ir.exports`

**Ordenação padrão:** `name, id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Export Name
- `resource` **(char)** — Resource
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `export_fields` **(one2many)** — Export ID → `ir.exports.line`
