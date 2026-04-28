# Theme Attachments — `theme.ir.attachment`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `key` **(char)** — Key ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `url` **(char)** — Url
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `copy_ids` **(one2many)** — Attachment using a copy of me 🔒 readonly → `ir.attachment`
