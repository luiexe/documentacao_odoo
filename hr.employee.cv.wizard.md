# Print Resume — `hr.employee.cv.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `color_primary` **(char)** — Primary Color ⚠️ obrigatório
- `color_secondary` **(char)** — Secondary Color ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `show_skills` **(boolean)** — Skills
- `show_contact` **(boolean)** — Contact Information
- `show_others` **(boolean)** — Others
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `employee_ids` **(many2many)** — Employee → `hr.employee`

## Campos Calculados (readonly)

- `can_show_others` **(boolean)** — Can Show Others 🔒 readonly
- `can_show_skills` **(boolean)** — Can Show Skills 🔒 readonly
