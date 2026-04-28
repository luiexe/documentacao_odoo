# Signature Document — `sign.document`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `attachment_id` **(many2one)** — Attachment ⚠️ obrigatório → `ir.attachment`
- `template_id` **(many2one)** — Template ⚠️ obrigatório → `sign.template`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `datas` **(binary)** — File Content (base64)
- `name` **(char)** — Name
- `num_pages` **(integer)** — Number of pages 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `sign_item_ids` **(one2many)** — Signature Items → `sign.item`
