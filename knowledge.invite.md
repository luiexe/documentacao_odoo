# Knowledge Invite Wizard — `knowledge.invite`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `article_id` **(many2one)** — Article ⚠️ obrigatório → `knowledge.article`
- `partner_ids` **(many2many)** — Recipients ⚠️ obrigatório → `res.partner`
- `permission` **(selection)** — Permission ⚠️ obrigatório
  > Opções: `write` (Can edit), `read` (Can read), `none` (No access)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `message` **(html)** — Message
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `have_share_partners` **(boolean)** — Have Share Partners 🔒 readonly
