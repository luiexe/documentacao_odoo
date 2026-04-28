# Planning Role — `planning.role`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `color` **(integer)** — Color
- `sequence` **(integer)** — Sequence
- `slot_properties_definition` **(properties_definition)** — Planning Slot Properties
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `resource_ids` **(many2many)** — Resources → `resource.resource`
- `product_ids` **(one2many)** — Services → `product.template`
