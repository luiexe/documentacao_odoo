# Appraisal Goal — `hr.appraisal.goal`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `progression` **(selection)** — Progress ⚠️ obrigatório
  > Opções: `000` (0%), `025` (25%), `050` (50%), `075` (75%), `100` (100%)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(html)** — Description
- `deadline` **(date)** — Deadline
- `number_of_sibling_goals` **(integer)** — Number Of Sibling Goals 🔒 readonly
- `number_of_completed_sibling_goals` **(integer)** — Number Of Completed Sibling Goals 🔒 readonly
- `sibling_goals_ratio` **(float)** — Sibling Goals Ratio 🔒 readonly
- `active` **(boolean)** — Active
- `parent_path` **(char)** — Parent Path
- `usual_duration_month` **(integer)** — Usual Timing
  > The average timing for the goals to be completed. It will populate the estimated end date when assigned
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `employee_ids` **(many2many)** — Employee → `hr.employee`
- `employee_autocomplete_ids` **(many2many)** — Employee Autocomplete 🔒 readonly → `hr.employee`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `manager_ids` **(many2many)** — Manager → `hr.employee`
- `department_ids` **(many2many)** — Department 🔒 readonly → `hr.department`
- `job_ids` **(many2many)** — Job 🔒 readonly → `hr.job`
- `tag_ids` **(many2many)** — Tags → `hr.appraisal.goal.tag`
- `template_goal_id` **(many2one)** — Goal Template → `hr.appraisal.goal`
- `parent_id` **(many2one)** — Parent Goal Template → `hr.appraisal.goal`
- `child_ids` **(one2many)** — Sub Goal Template → `hr.appraisal.goal`
- `goal_skill_ids` **(one2many)** — Skills → `hr.appraisal.goal.skill`
- `current_goal_skill_ids` **(one2many)** — Current Goal Skill → `hr.appraisal.goal.skill`
  > This goal will be recommended to reach the level of those skills.

## Campos Calculados (readonly)

- `is_manager` **(boolean)** — Is Manager 🔒 readonly
- `has_edit_right` **(boolean)** — Has Edit Right 🔒 readonly
