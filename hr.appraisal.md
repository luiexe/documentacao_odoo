# Employee Appraisal — `hr.appraisal`

**Ordenação padrão:** `state, date_close, id desc`

---

## Campos Obrigatórios

- `employee_id` **(many2one)** — Employee ⚠️ obrigatório → `hr.employee`
- `date_close` **(date)** — Appraisal Date ⚠️ obrigatório
  > Closing date of the current appraisal
- `state` **(selection)** — Status ⚠️ obrigatório
  > Opções: `1_new` (Draft), `2_pending` (Ongoing), `3_done` (Done)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `next_appraisal_date` **(date)** — Next Appraisal Date
  > Date where the new appraisal will be automatically created
- `accessible_employee_feedback` **(html)** — Accessible Employee Feedback
- `accessible_manager_feedback` **(html)** — Accessible Manager Feedback
- `employee_feedback_published` **(boolean)** — Employee Feedback Published
  > If greened, the manager will be able to see and edit your feedback. Otherwise, your feedback is blurred and visible only to you.
- `manager_feedback_published` **(boolean)** — Manager Feedback Published
  > If greened, the employee will be able to see your feedback. Otherwise, your feedback is blurred and visible only to you.
- `note` **(html)** — Private Note
- `appraisal_plan_posted` **(boolean)** — Appraisal Plan Posted
- `appraisal_properties` **(properties)** — Properties
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `employee_user_id` **(many2one)** — Employee User 🔒 readonly → `res.users`
  > Related user name for the resource to manage its access.
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `department_id` **(many2one)** — Department 🔒 readonly → `hr.department`
- `job_id` **(many2one)** — Job 🔒 readonly → `hr.job`
- `last_appraisal_id` **(many2one)** — Last Appraisal 🔒 readonly → `hr.appraisal`
- `appraisal_template_id` **(many2one)** — Appraisal Template → `hr.appraisal.template`
- `manager_ids` **(many2many)** — Manager → `hr.employee`
- `employee_autocomplete_ids` **(many2many)** — Employee Autocomplete 🔒 readonly → `hr.employee`
- `assessment_note` **(many2one)** — Final Rating → `hr.appraisal.note`
  > This field is not visible to the Employee.
- `duplicate_appraisal_id` **(many2one)** — Duplicate Appraisal 🔒 readonly → `hr.appraisal`
- `target_job_id` **(many2one)** — Target Job → `hr.job`
- `appraisal_skill_ids` **(one2many)** — Skills → `hr.appraisal.skill`
- `current_appraisal_skill_ids` **(one2many)** — Current Appraisal Skill → `hr.appraisal.skill`
- `employee_feedback_ids` **(many2many)** — Asked Feedback → `hr.employee`
- `survey_ids` **(many2many)** — Survey → `survey.survey`
  > Sent out surveys

## Campos Calculados (readonly)

- `image_128` **(binary)** — Image 128 🔒 readonly
- `image_1920` **(binary)** — Image 🔒 readonly
- `avatar_128` **(binary)** — Avatar 128 🔒 readonly
- `avatar_1920` **(binary)** — Avatar 🔒 readonly
- `employee_appraisal_count` **(integer)** — Appraisal Count 🔒 readonly
- `uncomplete_goals_count` **(integer)** — Uncomplete Goals Count 🔒 readonly
- `employee_feedback_template` **(html)** — Employee Feedback Template 🔒 readonly
- `manager_feedback_template` **(html)** — Manager Feedback Template 🔒 readonly
- `is_manager` **(boolean)** — Is Manager 🔒 readonly
- `waiting_feedback` **(boolean)** — Waiting Feedback from Employee/Managers 🔒 readonly
- `show_employee_feedback_full` **(boolean)** — Show Employee Feedback Full 🔒 readonly
- `show_manager_feedback_full` **(boolean)** — Show Manager Feedback Full 🔒 readonly
- `can_see_employee_publish` **(boolean)** — Can See Employee Publish 🔒 readonly
- `can_see_manager_publish` **(boolean)** — Can See Manager Publish 🔒 readonly
- `completed_survey_count` **(integer)** — Completed Survey Count 🔒 readonly
- `total_survey_count` **(integer)** — Total Survey Count 🔒 readonly
