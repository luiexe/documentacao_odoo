# Appraisal Campaign Wizard — `hr.appraisal.campaign.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `mode` **(selection)** — Mode ⚠️ obrigatório
  > Allow to create appraisals in batches: - By Employee: for specific employees - By Company: all employees of the specified company - By Department: all employees of the specified department - By Employee Tag: all employees of the specific employee group category
  > Opções: `employee` (By Employee), `company` (By Company), `department` (By Department), `category` (By Employee Tag)
- `appraisal_template_id` **(many2one)** — Appraisal Template ⚠️ obrigatório → `hr.appraisal.template`
- `appraisal_date` **(date)** — Appraisal Date ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `manager` **(selection)** — Manager
  > 'Employee's Manager': Each appraisal will be conducted by the direct manager of the employee 'Specific Person': All appraisals will be conducted by the specified employees
  > Opções: `employee_manager` (Employee's Manager), `person` (Other)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `employee_ids` **(many2many)** — Employees → `hr.employee`
- `department_id` **(many2one)** — Department → `hr.department`
- `company_id` **(many2one)** — Company → `res.company`
- `category_id` **(many2one)** — Employee Tag → `hr.employee.category`
- `manager_ids` **(many2many)** — Managers → `hr.employee`

## Campos Calculados (readonly)

- `warning` **(char)** — Warning 🔒 readonly
