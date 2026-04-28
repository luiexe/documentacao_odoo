# Asset — `ir.asset`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `bundle` **(char)** — Bundle name ⚠️ obrigatório
- `path` **(char)** — Path (or glob pattern) ⚠️ obrigatório
- `sequence` **(integer)** — Sequence ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `directive` **(selection)** — Directive
  > Opções: `append` (Append), `prepend` (Prepend), `after` (After), `before` (Before), `remove` (Remove), `replace` (Replace), `include` (Include)
- `target` **(char)** — Target
- `active` **(boolean)** — active
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `key` **(char)** — Key

## Relacionamentos

- `website_id` **(many2one)** — Website → `website`
- `theme_template_id` **(many2one)** — Theme Template → `theme.ir.asset`
