# Accounting Return Check — `account.return.check`

**Ordenação padrão:** `name, id`

---

## Campos Obrigatórios

- `code` **(char)** — Check ID ⚠️ obrigatório
- `type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `check` (Check), `file` (Upload Document)
- `name` **(char)** — Name ⚠️ obrigatório
- `state` **(char)** — Return State To Check For ⚠️ obrigatório
- `result` **(selection)** — Result ⚠️ obrigatório
  > Opções: `todo` (To Review), `reviewed` (Reviewed), `supervised` (Supervised), `anomaly` (Anomaly)
- `return_id` **(many2one)** — Account Return ⚠️ obrigatório → `account.return`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `message` **(text)** — Description
- `records_count` **(integer)** — Records Count 🔒 readonly
- `action` **(json)** — Action
- `return_state` **(char)** — Return State 🔒 readonly
- `refresh_result` **(boolean)** — Refresh Result
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `template_id` **(many2one)** — Template → `account.return.check.template`
- `records_model` **(many2one)** — Model → `ir.model`
- `attachment_ids` **(many2many)** — Attachment → `ir.attachment`
- `approver_ids` **(many2many)** — Approved By 🔒 readonly → `res.users`
- `supervisor_id` **(many2one)** — Supervised By 🔒 readonly → `res.users`
- `approver_supervisor_ids` **(many2many)** — Approvers and Supervisor 🔒 readonly → `res.users`

## Campos Calculados (readonly)

- `records_name` **(char)** — Records Name 🔒 readonly
- `is_return_active` **(boolean)** — Active 🔒 readonly
- `return_name` **(char)** — Return Name 🔒 readonly
- `date_deadline` **(date)** — Deadline 🔒 readonly
- `cycle` **(selection)** — Cycle 🔒 readonly
  > Opções: `regulatory_compliance` (Regulatory compliance), `treasury_financing` (Treasury and financing), `purchases` (Purchases), `operating_expenses` (Operating expenses), `sales` (Sales), `inventory` (Inventory), `fixed_assets` (Fixed assets), `payroll` (Payroll), `state` (Government), `equity` (Equity), `other` (Others)
