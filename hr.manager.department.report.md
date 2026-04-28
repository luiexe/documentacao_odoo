# Hr Manager Department Report — `hr.manager.department.report`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly

## Relacionamentos

- `employee_id` **(many2one)** — Employee 🔒 readonly → `hr.employee`

## Campos Calculados (readonly)

- `has_department_manager_access` **(boolean)** — Has Department Manager Access 🔒 readonly
