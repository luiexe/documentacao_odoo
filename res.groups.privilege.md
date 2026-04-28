# Privileges — `res.groups.privilege`

**Ordenação padrão:** `sequence, name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(text)** — Description
- `placeholder` **(char)** — Placeholder
  > Text that is displayed as placeholder in the selection field of the user form.
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `category_id` **(many2one)** — Category → `ir.module.category`
- `group_ids` **(one2many)** — Groups → `res.groups`
