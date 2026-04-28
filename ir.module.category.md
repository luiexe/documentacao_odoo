# Application — `ir.module.category`

**Ordenação padrão:** `sequence, name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(text)** — Description
- `sequence` **(integer)** — Sequence
- `visible` **(boolean)** — Visible
- `exclusive` **(boolean)** — Exclusive
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `parent_id` **(many2one)** — Parent Application → `ir.module.category`
- `child_ids` **(one2many)** — Child Applications → `ir.module.category`
- `module_ids` **(one2many)** — Modules → `ir.module.module`
- `privilege_ids` **(one2many)** — Privileges → `res.groups.privilege`

## Campos Calculados (readonly)

- `xml_id` **(char)** — External ID 🔒 readonly
