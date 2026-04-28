# Annual Report — `audit.report`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `knowledge_article_id` **(many2one)** — Article ⚠️ obrigatório → `knowledge.article`
- `title` **(char)** — Title ⚠️ obrigatório
- `start_date` **(date)** — Start Date ⚠️ obrigatório
  > Start Date, included in the fiscal year.
- `end_date` **(date)** — End Date ⚠️ obrigatório
  > Ending Date, included in the fiscal year.
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `knowledge_template_article_id` **(many2one)** — Annual Report Template ⚠️ obrigatório → `knowledge.article`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `color` **(integer)** — Color Index
- `status` **(selection)** — Status
  > Opções: `draft` (Draft), `done` (Done)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `responsible_user_ids` **(many2many)** — Responsibles → `res.users`
