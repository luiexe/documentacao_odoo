# Approval Category — `approval.category`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `has_date` **(selection)** — Has Date ⚠️ obrigatório
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_period` **(selection)** — Has Period ⚠️ obrigatório
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_quantity` **(selection)** — Has Quantity ⚠️ obrigatório
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_amount` **(selection)** — Has Amount ⚠️ obrigatório
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_reference` **(selection)** — Has Reference ⚠️ obrigatório
  > An additional reference that should be specified on the request.
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_partner` **(selection)** — Has Contact ⚠️ obrigatório
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_payment_method` **(selection)** — Has Payment ⚠️ obrigatório
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_location` **(selection)** — Has Location ⚠️ obrigatório
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_product` **(selection)** — Has Product ⚠️ obrigatório
  > Additional products that should be specified on the request.
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `requirer_document` **(selection)** — Documents ⚠️ obrigatório
  > Opções: `required` (Required), `optional` (Optional)
- `approval_minimum` **(integer)** — Minimum Approval ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
- `description` **(char)** — Description
- `image` **(binary)** — Image
- `approval_type` **(selection)** — Approval Type
  > Allows you to define which documents you would like to create once the request has been approved
  > Opções: `purchase` (Create RFQ's)
- `manager_approval` **(selection)** — Employee's Manager
  > How the employee's manager interacts with this type of approval.          Empty: do nothing         Is Approver: the employee's manager will be in the approver list         Is Required Approver: the employee's manager will be required to approve the request.     
  > Opções: `approver` (Is Approver), `required` (Is Required Approver)
- `approver_sequence` **(boolean)** — Approvers Sequence?
  > If checked, the approvers have to approve in sequence (one after the other). If Employee's Manager is selected as approver, they will be the first in line.
- `automated_sequence` **(boolean)** — Automated Sequence?
  > If checked, the Approval Requests will have an automated generated name based on the given code.
- `sequence_code` **(char)** — Code
- `approval_properties_definition` **(properties_definition)** — Approval Properties
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_ids` **(many2many)** — Approver Users 🔒 readonly → `res.users`
- `approver_ids` **(one2many)** — Approvers → `approval.category.approver`
- `sequence_id` **(many2one)** — Reference Sequence → `ir.sequence`

## Campos Calculados (readonly)

- `invalid_minimum` **(boolean)** — Invalid Minimum 🔒 readonly
- `invalid_minimum_warning` **(char)** — Invalid Minimum Warning 🔒 readonly
- `request_to_validate_count` **(integer)** — Number of requests to validate 🔒 readonly
