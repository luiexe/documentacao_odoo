# Departure Wizard — `hr.departure.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `departure_reason_id` **(many2one)** — Departure Reason ⚠️ obrigatório → `hr.departure.reason`
- `departure_date` **(date)** — Contract End Date ⚠️ obrigatório
- `employee_ids` **(many2many)** — Employees ⚠️ obrigatório → `hr.employee`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `departure_description` **(html)** — Additional Information
- `remove_related_user` **(boolean)** — Related User
  > If checked, the related user will be removed from the system.
- `set_date_end` **(boolean)** — Set Contract End Date
  > Set the end date on the current contract.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `delete_appraisal` **(boolean)** — Delete Future Appraisals
  > Delete all appraisal after contract end date.

## Campos Calculados (readonly)

- `is_user_employee` **(boolean)** — User Employee 🔒 readonly
