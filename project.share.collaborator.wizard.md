# Project Sharing Collaborator Wizard — `project.share.collaborator.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `partner_id` **(many2one)** — Collaborator ⚠️ obrigatório → `res.partner`
- `access_mode` **(selection)** — Access Mode ⚠️ obrigatório
  > Read: collaborators can view tasks but cannot edit them. Edit with limited access: collaborators can view and edit tasks they follow in the Kanban view. Edit: collaborators can view and edit all tasks in the Kanban view. Additionally, they can choose which tasks they want to follow.
  > Opções: `read` (Read), `edit_limited` (Edit with limited access), `edit` (Edit)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `send_invitation` **(boolean)** — Send Invitation
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `parent_wizard_id` **(many2one)** — Parent Wizard → `project.share.wizard`
