# Module Uninstall — `base.module.uninstall`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `module_ids` **(many2many)** — Module(s) ⚠️ obrigatório 🔒 readonly → `ir.module.module`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `show_all` **(boolean)** — Show All
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `impacted_module_ids` **(many2many)** — Impacted modules 🔒 readonly → `ir.module.module`
- `model_ids` **(many2many)** — Impacted data models 🔒 readonly → `ir.model`

## Campos Calculados (readonly)

- `is_studio` **(boolean)** — Is Studio 🔒 readonly
- `custom_views` **(integer)** — Custom Views 🔒 readonly
- `custom_reports` **(integer)** — Custom Reports 🔒 readonly
- `custom_models` **(integer)** — Custom Models 🔒 readonly
- `custom_fields` **(integer)** — Custom Fields 🔒 readonly
