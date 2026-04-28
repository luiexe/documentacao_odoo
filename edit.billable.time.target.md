# Edit Billable Time Target wizard from Timesheet for users without employee access — `edit.billable.time.target`

**Ordenação padrão:** `name`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Create Date 🔒 readonly
- `name` **(char)** — Name 🔒 readonly
- `billable_time_target` **(float)** — Monthly Billing Time Target
- `work_email` **(char)** — Work Email 🔒 readonly
- `work_phone` **(char)** — Work Phone 🔒 readonly
- `mobile_phone` **(char)** — Mobile Phone 🔒 readonly
- `active` **(boolean)** — Active 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `employee_id` **(many2one)** — Employee 🔒 readonly → `hr.employee`
- `resource_calendar_id` **(many2one)** — Working Hours 🔒 readonly → `resource.calendar`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `department_id` **(many2one)** — Department 🔒 readonly → `hr.department`
- `job_id` **(many2one)** — Job Position 🔒 readonly → `hr.job`
- `parent_id` **(many2one)** — Manager 🔒 readonly → `hr.employee.public`
- `child_ids` **(one2many)** — Direct subordinates → `hr.employee.public`
- `address_id` **(many2one)** — Work Address 🔒 readonly → `res.partner`
- `work_location_id` **(many2one)** — Work Location 🔒 readonly → `hr.work.location`
- `timesheet_manager_id` **(many2one)** — Timesheet Approver 🔒 readonly → `res.users`
- `user_id` **(many2one)** — User 🔒 readonly → `res.users`
- `coach_id` **(many2one)** — Coach 🔒 readonly → `hr.employee.public`

## Campos Calculados (readonly)

- `work_location_name` **(char)** — Work Location Name 🔒 readonly
- `show_hr_icon_display` **(boolean)** — Show Hr Icon Display 🔒 readonly
- `hr_icon_display` **(selection)** — Hr Icon Display 🔒 readonly
  > Opções: `presence_present` (Present), `presence_out_of_working_hour` (Off-Hours), `presence_absent` (Absent), `presence_archive` (Archived), `presence_undetermined` (Undetermined), `presence_home` (At Home), `presence_office` (At Office), `presence_other` (At Other)
- `hr_presence_state` **(selection)** — Hr Presence State 🔒 readonly
  > Opções: `present` (Present), `absent` (Absent), `archive` (Archived), `out_of_working_hour` (Off-Hours)
- `image_128` **(binary)** — Image 128 🔒 readonly
- `avatar_128` **(binary)** — Avatar 128 🔒 readonly
- `avatar_1920` **(binary)** — Avatar 1920 🔒 readonly
- `image_1024` **(binary)** — Image 1024 🔒 readonly
- `birthday_public_display_string` **(char)** — Public Date of Birth 🔒 readonly
- `member_of_department` **(boolean)** — Member of department 🔒 readonly
  > Whether the employee is a member of the active user's department or one of it's child department.
- `newly_hired` **(boolean)** — Newly Hired 🔒 readonly
