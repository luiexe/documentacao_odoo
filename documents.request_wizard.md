# Document Request — `documents.request_wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `requestee_id` **(many2one)** — Owner ⚠️ obrigatório → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `res_model` **(char)** — Resource Model
- `res_id` **(integer)** — Resource ID
- `activity_note` **(html)** — Message
- `activity_date_deadline_range` **(integer)** — Due Date In
- `activity_date_deadline_range_type` **(selection)** — Due type
  > Opções: `days` (Days), `weeks` (Weeks), `months` (Months)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `partner_id` **(many2one)** — Contact → `res.partner`
- `tag_ids` **(many2many)** — Tags → `documents.tag`
- `folder_id` **(many2one)** — Folder → `documents.document`
