# Document Followers — `mail.followers`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `res_model` **(char)** — Related Document Model Name ⚠️ obrigatório
- `partner_id` **(many2one)** — Related Partner ⚠️ obrigatório → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `res_id` **(many2one_reference)** — Related Document ID
  > Id of the followed resource

## Relacionamentos

- `subtype_ids` **(many2many)** — Subtype → `mail.message.subtype`
  > Message subtypes followed, meaning subtypes that will be pushed onto the user's Wall.

## Campos Calculados (readonly)

- `name` **(char)** — Name 🔒 readonly
- `email` **(char)** — Email 🔒 readonly
- `is_active` **(boolean)** — Is Active 🔒 readonly
