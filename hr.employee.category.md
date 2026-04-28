# Employee Category — `hr.employee.category`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Tag Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `color` **(integer)** — Color Index
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `employee_ids` **(many2many)** — Employees → `hr.employee`
