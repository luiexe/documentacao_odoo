# Favorite Article — `knowledge.article.favorite`

**Ordenação padrão:** `sequence ASC, id DESC`

---

## Campos Obrigatórios

- `article_id` **(many2one)** — Article ⚠️ obrigatório → `knowledge.article`
- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `is_article_active` **(boolean)** — Is Article Active 🔒 readonly
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
