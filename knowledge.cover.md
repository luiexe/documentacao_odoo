# Knowledge Cover — `knowledge.cover`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `attachment_id` **(many2one)** — Cover attachment ⚠️ obrigatório → `ir.attachment`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `attachment_url` **(char)** — Cover URL 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `article_ids` **(one2many)** — Articles using cover → `knowledge.article`
