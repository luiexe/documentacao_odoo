# Article Member — `knowledge.article.member`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `article_id` **(many2one)** — Article ⚠️ obrigatório → `knowledge.article`
- `partner_id` **(many2one)** — Partner ⚠️ obrigatório → `res.partner`
- `permission` **(selection)** — Permission ⚠️ obrigatório
  > Opções: `write` (Can edit), `read` (Can read), `none` (No access)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `article_permission` **(selection)** — Inherited Permission 🔒 readonly
  > Opções: `write` (Can edit), `read` (Can read), `none` (Members only)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `article_member_avatar` **(binary)** — Avatar 128 🔒 readonly
