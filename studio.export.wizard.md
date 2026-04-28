# Studio Export Wizard — `studio.export.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `include_additional_data` **(boolean)** — Include Data
- `include_demo_data` **(boolean)** — Include Demo Data
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `default_export_data` **(many2many)** — Default Export Data → `studio.export.wizard.data`
- `additional_models` **(many2many)** — Additional models to export 🔒 readonly → `studio.export.model`
  > Additional models you may choose to export in addition to the Studio customizations
- `additional_export_data` **(many2many)** — Additional Export Data 🔒 readonly → `studio.export.wizard.data`
