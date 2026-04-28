# Production Group — `mrp.production.group`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `production_ids` **(one2many)** — Productions → `mrp.production`
- `child_ids` **(many2many)** — Child Manufacturing Orders → `mrp.production.group`
- `parent_ids` **(many2many)** — Parent Manufacturing Orders → `mrp.production.group`
