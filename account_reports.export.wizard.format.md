# Export format for accounting's reports — `account_reports.export.wizard.format`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `fun_to_call` **(char)** — Function to Call ⚠️ obrigatório
- `export_wizard_id` **(many2one)** — Parent Wizard ⚠️ obrigatório → `account_reports.export.wizard`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `fun_param` **(char)** — Function Parameter
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
