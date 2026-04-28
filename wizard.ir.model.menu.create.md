# Create Menu Wizard — `wizard.ir.model.menu.create`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `menu_id` **(many2one)** — Parent Menu ⚠️ obrigatório → `ir.ui.menu`
- `name` **(char)** — Menu Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
