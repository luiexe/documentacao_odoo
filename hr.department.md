# Department — `hr.department`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `name` **(char)** — Department Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `has_read_access` **(boolean)** — Has Read Access
- `note` **(text)** — Note
- `color` **(integer)** — Color Index
- `parent_path` **(char)** — Parent Path
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `appraisal_properties_definition` **(properties_definition)** — Appraisal Properties

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `parent_id` **(many2one)** — Parent Department → `hr.department`
- `child_ids` **(one2many)** — Child Departments → `hr.department`
- `manager_id` **(many2one)** — Manager → `hr.employee`
- `member_ids` **(one2many)** — Members 🔒 readonly → `hr.employee`
- `jobs_ids` **(one2many)** — Jobs → `hr.job`
- `plan_ids` **(one2many)** — Plan → `mail.activity.plan`
- `master_department_id` **(many2one)** — Master Department 🔒 readonly → `hr.department`
- `appraisal_template_ids` **(many2many)** — Appraisal Templates → `hr.appraisal.template`

## Campos Calculados (readonly)

- `complete_name` **(char)** — Complete Name 🔒 readonly
- `total_employee` **(integer)** — Total Employee 🔒 readonly
- `plans_count` **(integer)** — Plans Count 🔒 readonly
- `expenses_to_approve_count` **(integer)** — Expenses to Approve 🔒 readonly
- `new_applicant_count` **(integer)** — New Applicant 🔒 readonly
- `new_hired_employee` **(integer)** — New Hired Employee 🔒 readonly
- `expected_employee` **(integer)** — Expected Employee 🔒 readonly
- `appraisals_to_process_count` **(integer)** — Appraisals to Process 🔒 readonly
