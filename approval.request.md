# Approval Request — `approval.request`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `category_id` **(many2one)** — Category ⚠️ obrigatório → `approval.category`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Approval Subject
- `active` **(boolean)** — Active
- `date` **(datetime)** — Date
- `date_start` **(datetime)** — Date start
- `date_end` **(datetime)** — Date end
- `quantity` **(float)** — Quantity
- `location` **(char)** — Location
- `date_confirmed` **(datetime)** — Date Confirmed
- `reference` **(char)** — Reference
- `amount` **(float)** — Amount
- `reason` **(html)** — Description
- `request_status` **(selection)** — Request Status 🔒 readonly
  > Opções: `new` (To Submit), `pending` (Submitted), `approved` (Approved), `refused` (Refused), `cancel` (Canceled)
- `approval_properties` **(properties)** — Properties
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `message_main_attachment_id` **(many2one)** — Main Attachment → `ir.attachment`
- `approver_ids` **(one2many)** — Approvers → `approval.approver`
- `user_ids` **(many2many)** — Users 🔒 readonly → `res.users`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `partner_id` **(many2one)** — Contact → `res.partner`
- `request_owner_id` **(many2one)** — Request Owner → `res.users`
- `attachment_ids` **(one2many)** — Attachments → `ir.attachment`
- `product_line_ids` **(one2many)** — Product Line → `approval.product.line`

## Campos Calculados (readonly)

- `category_image` **(binary)** — Image 🔒 readonly
- `user_status` **(selection)** — User Status 🔒 readonly
  > Opções: `new` (New), `pending` (Submitted), `waiting` (Waiting), `approved` (Approved), `refused` (Refused), `cancel` (Canceled)
- `has_access_to_request` **(boolean)** — Has Access To Request 🔒 readonly
- `change_request_owner` **(boolean)** — Can Change Request Owner 🔒 readonly
- `attachment_number` **(integer)** — Number of Attachments 🔒 readonly
- `has_date` **(selection)** — Has Date 🔒 readonly
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_period` **(selection)** — Has Period 🔒 readonly
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_quantity` **(selection)** — Has Quantity 🔒 readonly
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_amount` **(selection)** — Has Amount 🔒 readonly
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_reference` **(selection)** — Has Reference 🔒 readonly
  > An additional reference that should be specified on the request.
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_partner` **(selection)** — Has Contact 🔒 readonly
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_payment_method` **(selection)** — Has Payment 🔒 readonly
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_location` **(selection)** — Has Location 🔒 readonly
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `has_product` **(selection)** — Has Product 🔒 readonly
  > Additional products that should be specified on the request.
  > Opções: `required` (Required), `optional` (Optional), `no` (None)
- `requirer_document` **(selection)** — Documents 🔒 readonly
  > Opções: `required` (Required), `optional` (Optional)
- `approval_minimum` **(integer)** — Minimum Approval 🔒 readonly
- `approval_type` **(selection)** — Approval Type 🔒 readonly
  > Allows you to define which documents you would like to create once the request has been approved
  > Opções: `purchase` (Create RFQ's)
- `approver_sequence` **(boolean)** — Approvers Sequence? 🔒 readonly
  > If checked, the approvers have to approve in sequence (one after the other). If Employee's Manager is selected as approver, they will be the first in line.
- `automated_sequence` **(boolean)** — Automated Sequence? 🔒 readonly
  > If checked, the Approval Requests will have an automated generated name based on the given code.
- `purchase_order_count` **(integer)** — Purchase Order Count 🔒 readonly
- `documents_count` **(integer)** — Documents Count 🔒 readonly
- `documents_enabled` **(boolean)** — Documents Approvals Settings 🔒 readonly
- `hide_location` **(boolean)** — Hide Location 🔒 readonly
