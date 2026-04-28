# planning calendar resource — `planning.calendar.resource`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `user_id` **(many2one)** — Me ⚠️ obrigatório → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `checked` **(boolean)** — Checked
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `resource_id` **(many2one)** — resource → `resource.resource`

## Campos Calculados (readonly)

- `resource_type` **(selection)** — Type 🔒 readonly
  > Opções: `user` (Human), `material` (Material)
