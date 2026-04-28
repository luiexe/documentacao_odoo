# Project Sharing — `project.share.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `res_model` **(char)** — Related Document Model ⚠️ obrigatório
- `res_id` **(integer)** — Related Document ID ⚠️ obrigatório
- `partner_ids` **(many2many)** — Recipients ⚠️ obrigatório → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `note` **(text)** — Note
  > Add extra content to display in the email
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `collaborator_ids` **(one2many)** — Collaborators → `project.share.collaborator.wizard`
- `existing_partner_ids` **(many2many)** — Existing Partner 🔒 readonly → `res.partner`

## Campos Calculados (readonly)

- `resource_ref` **(reference)** — Related Document 🔒 readonly
  > Opções: `project.project` (Project)
- `share_link` **(char)** — Public Link 🔒 readonly
  > Anyone with this link can access the project in read mode.
- `access_warning` **(text)** — Access warning 🔒 readonly
