# Partner Tags — `res.partner.category`

**Ordenação padrão:** `name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `color` **(integer)** — Color
- `active` **(boolean)** — Active
  > The active field allows you to hide the category without removing it.
- `parent_path` **(char)** — Parent Path
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `parent_id` **(many2one)** — Category → `res.partner.category`
- `child_ids` **(one2many)** — Child Tags → `res.partner.category`
- `partner_ids` **(many2many)** — Partners → `res.partner`
