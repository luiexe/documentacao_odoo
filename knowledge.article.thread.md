# Article Discussion Thread — `knowledge.article.thread`

**Ordenação padrão:** `write_date desc, id desc`

---

## Campos Obrigatórios

- `article_id` **(many2one)** — Article ⚠️ obrigatório 🔒 readonly → `knowledge.article`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `article_anchor_text` **(text)** — Anchor Text
  > The original highlighted anchor text, giving initial context if that text is modified or removed afterwards.
- `is_resolved` **(boolean)** — Thread Closed
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
