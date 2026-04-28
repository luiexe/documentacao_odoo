# Module Activation Review — `base.module.install.review`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `module_id` **(many2one)** — Module ⚠️ obrigatório 🔒 readonly → `ir.module.module`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `module_ids` **(many2many)** — Depending Apps 🔒 readonly → `ir.module.module`

## Campos Calculados (readonly)

- `modules_description` **(html)** — Modules Description 🔒 readonly
