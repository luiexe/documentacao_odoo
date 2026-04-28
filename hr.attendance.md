# Attendance — `hr.attendance`

**Ordenação padrão:** `check_in desc`

---

## Campos Obrigatórios

- `employee_id` **(many2one)** — Employee ⚠️ obrigatório → `hr.employee`
- `check_in` **(datetime)** — Check In ⚠️ obrigatório
- `date` **(date)** — Date ⚠️ obrigatório 🔒 readonly

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `check_out` **(datetime)** — Check Out
- `worked_hours` **(float)** — Worked Hours 🔒 readonly
- `overtime_hours` **(float)** — Over Time 🔒 readonly
- `overtime_status` **(selection)** — Overtime Status
  > Opções: `to_approve` (To Approve), `approved` (Approved), `refused` (Refused)
- `validated_overtime_hours` **(float)** — Extra Hours 🔒 readonly
- `in_latitude` **(float)** — Latitude 🔒 readonly
- `in_longitude` **(float)** — Longitude 🔒 readonly
- `in_location` **(char)** — In Location
  > Based on GPS-Coordinates if available or on IP Address
- `in_ip_address` **(char)** — IP Address 🔒 readonly
- `in_browser` **(char)** — Browser 🔒 readonly
- `in_mode` **(selection)** — Mode 🔒 readonly
  > Opções: `kiosk` (Kiosk), `systray` (Systray), `manual` (Manual), `technical` (Technical)
- `out_latitude` **(float)** — Out Latitude 🔒 readonly
- `out_longitude` **(float)** — Out Longitude 🔒 readonly
- `out_location` **(char)** — Out Location
  > Based on GPS-Coordinates if available or on IP Address
- `out_ip_address` **(char)** — Out Ip Address 🔒 readonly
- `out_browser` **(char)** — Out Browser 🔒 readonly
- `out_mode` **(selection)** — Out Mode 🔒 readonly
  > Opções: `kiosk` (Kiosk), `systray` (Systray), `manual` (Manual), `technical` (Technical), `auto_check_out` (Automatic Check-Out)
- `expected_hours` **(float)** — Theoretical Hours 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `department_id` **(many2one)** — Department 🔒 readonly → `hr.department`
- `manager_id` **(many2one)** — Manager 🔒 readonly → `hr.employee`
- `linked_overtime_ids` **(many2many)** — Linked Overtime → `hr.attendance.overtime.line`

## Campos Calculados (readonly)

- `is_manager` **(boolean)** — Is Manager 🔒 readonly
- `color` **(integer)** — Color 🔒 readonly
- `device_tracking_enabled` **(boolean)** — Device & Location Tracking 🔒 readonly
- `overtime_progress` **(float)** — Overtime Progress 🔒 readonly
