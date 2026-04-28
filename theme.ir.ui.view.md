# Theme UI View — `theme.ir.ui.view`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `priority` **(integer)** — Priority ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `key` **(char)** — Key
- `type` **(char)** — Type
- `mode` **(selection)** — Mode
  > Opções: `primary` (Base view), `extension` (Extension View)
- `active` **(boolean)** — Active
- `arch` **(text)** — Arch
- `arch_fs` **(char)** — Arch Fs
- `inherit_id` **(reference)** — Inherit
  > Opções: `ir.ui.view` (ir.ui.view), `theme.ir.ui.view` (theme.ir.ui.view)
- `customize_show` **(boolean)** — Customize Show
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `copy_ids` **(one2many)** — Views using a copy of me 🔒 readonly → `ir.ui.view`
