# Collaborators in project shared — `project.collaborator`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `project_id` **(many2one)** — Project Shared ⚠️ obrigatório 🔒 readonly → `project.project`
- `partner_id` **(many2one)** — Collaborator ⚠️ obrigatório 🔒 readonly → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `limited_access` **(boolean)** — Limited Access
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `partner_email` **(char)** — Email 🔒 readonly
