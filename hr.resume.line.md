# Resume line of an employee — `hr.resume.line`

**Ordenação padrão:** `line_type_id, date_end desc, date_start desc`

---

## Campos Obrigatórios

- `employee_id` **(many2one)** — Employee ⚠️ obrigatório → `hr.employee`
- `name` **(char)** — Name ⚠️ obrigatório
- `date_start` **(date)** — Date Start ⚠️ obrigatório
- `course_type` **(selection)** — Course Type ⚠️ obrigatório
  > Opções: `external` (External), `elearning` (eLearning)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date_end` **(date)** — Date End
- `duration` **(integer)** — Duration
- `description` **(html)** — Description
- `external_url` **(char)** — External URL
- `certificate_filename` **(char)** — Certificate Filename
- `certificate_file` **(binary)** — Certificate
- `resume_line_properties` **(properties)** — Properties
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `expiration_status` **(selection)** — Expiration Status 🔒 readonly
  > Opções: `expired` (Expired), `expiring` (Expiring), `valid` (Valid)

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `department_id` **(many2one)** — Department 🔒 readonly → `hr.department`
- `line_type_id` **(many2one)** — Type → `hr.resume.line.type`
- `survey_id` **(many2one)** — Certification 🔒 readonly → `survey.survey`
- `channel_id` **(many2one)** — eLearning Course 🔒 readonly → `slide.channel`

## Campos Calculados (readonly)

- `avatar_128` **(binary)** — Avatar 128 🔒 readonly
- `is_course` **(boolean)** — Course 🔒 readonly
- `color` **(char)** — Color 🔒 readonly
- `course_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
