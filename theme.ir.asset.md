# Theme Asset — `theme.ir.asset`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `bundle` **(char)** — Bundle ⚠️ obrigatório
- `path` **(char)** — Path ⚠️ obrigatório
- `sequence` **(integer)** — Sequence ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `key` **(char)** — Key
- `directive` **(selection)** — Directive
  > Opções: `append` (Append), `prepend` (Prepend), `after` (After), `before` (Before), `remove` (Remove), `replace` (Replace), `include` (Include)
- `target` **(char)** — Target
- `active` **(boolean)** — Active
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `copy_ids` **(one2many)** — Assets using a copy of me 🔒 readonly → `ir.asset`
