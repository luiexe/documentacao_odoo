# Menu — `ir.ui.menu`

**Ordenação padrão:** `sequence,id`

---

## Campos Obrigatórios

- `name` **(char)** — Menu ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
- `parent_path` **(char)** — Parent Path
- `web_icon` **(char)** — Web Icon File
- `action` **(reference)** — Action
  > Opções: `ir.actions.report` (ir.actions.report), `ir.actions.act_window` (ir.actions.act_window), `ir.actions.act_url` (ir.actions.act_url), `ir.actions.server` (ir.actions.server), `ir.actions.client` (ir.actions.client)
- `web_icon_data` **(binary)** — Web Icon Image
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `is_studio_configuration` **(boolean)** — Studio Configuration Menu 🔒 readonly
  > Indicates that this menu was created by Studio to hold configuration sub-menus

## Relacionamentos

- `child_id` **(one2many)** — Child IDs → `ir.ui.menu`
- `parent_id` **(many2one)** — Parent Menu → `ir.ui.menu`
- `group_ids` **(many2many)** — Groups → `res.groups`
  > If you have groups, the visibility of this menu will be based on these groups. If this field is empty, Odoo will compute visibility based on the related object's read access.

## Campos Calculados (readonly)

- `complete_name` **(char)** — Full Path 🔒 readonly
