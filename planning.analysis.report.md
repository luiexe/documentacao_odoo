# Planning Analysis Report — `planning.analysis.report`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `allocated_hours` **(float)** — Allocated Time 🔒 readonly
- `allocated_percentage` **(float)** — Allocated Time (%) 🔒 readonly
- `end_datetime` **(datetime)** — End Date 🔒 readonly
- `job_title` **(char)** — Job Title 🔒 readonly
- `name` **(text)** — Note 🔒 readonly
- `publication_warning` **(boolean)** — Modified Since Last Publication 🔒 readonly
  > If checked, it means that the shift contains has changed since its last publish.
- `resource_type` **(selection)** — Type 🔒 readonly
  > Opções: `user` (Human), `material` (Material)
- `start_datetime` **(datetime)** — Start Date 🔒 readonly
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Draft), `published` (Published)
- `request_to_switch` **(boolean)** — Has there been a request to switch on this shift slot? 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `department_id` **(many2one)** — Department 🔒 readonly → `hr.department`
- `employee_id` **(many2one)** — Employee 🔒 readonly → `hr.employee`
- `manager_id` **(many2one)** — Manager 🔒 readonly → `hr.employee`
- `recurrency_id` **(many2one)** — Recurrency 🔒 readonly → `planning.recurrency`
- `resource_id` **(many2one)** — Resource 🔒 readonly → `resource.resource`
- `role_id` **(many2one)** — Role 🔒 readonly → `planning.role`
- `user_id` **(many2one)** — User 🔒 readonly → `res.users`
- `slot_id` **(many2one)** — Planning Slot 🔒 readonly → `planning.slot`
- `employee_skill_ids` **(one2many)** — Skills 🔒 readonly → `hr.employee.skill`
- `sale_order_id` **(many2one)** — Sales Order 🔒 readonly → `sale.order`
- `sale_line_id` **(many2one)** — Sales Order Item 🔒 readonly → `sale.order.line`
- `role_product_ids` **(one2many)** — Role Product 🔒 readonly → `product.template`
