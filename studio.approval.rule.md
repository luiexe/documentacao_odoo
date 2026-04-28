# Studio Approval Rule — `studio.approval.rule`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `model_id` **(many2one)** — Model ⚠️ obrigatório → `ir.model`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `method` **(char)** — Method
- `name` **(char)** — Name
- `message` **(char)** — Description
  > The step description will be displayed on the button on which an approval is requested.
- `notification_order` **(selection)** — Step
  > Defines the sequential order in which the approvals are requested.
  > Opções: `1` (Step 1), `2` (Step 2), `3` (Step 3), `4` (Step 4), `5` (Step 5), `6` (Step 6), `7` (Step 7), `8` (Step 8), `9` (Step 9)
- `exclusive_user` **(boolean)** — Exclusive Approval
  > If set, the user who approves this rule will not be able to approve other rules for the same record
- `model_name` **(char)** — Model Name 🔒 readonly
- `domain` **(char)** — Domain
  > If set, the rule will only apply on records that match the domain.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `action_id` **(many2one)** — Action → `ir.actions.actions`
- `approver_ids` **(many2many)** — Approvers → `res.users`
  > These users are able to approve or reject the step and will be assigned to an activity when their approval is requested.
- `approver_log_ids` **(one2many)** — Approver Log → `studio.approval.rule.approver`
- `approval_group_id` **(many2one)** — Approval Group → `res.groups`
  > The users in this group are able to approve or reject the step.
- `users_to_notify` **(many2many)** — Users to Notify → `res.users`
  > These users will receive a notification via internal note when the step is approved or rejected
- `entry_ids` **(one2many)** — Entries → `studio.approval.entry`

## Campos Calculados (readonly)

- `action_xmlid` **(char)** — External ID 🔒 readonly
- `conditional` **(boolean)** — Conditional Rule 🔒 readonly
- `can_validate` **(boolean)** — Can be approved 🔒 readonly
  > Whether the rule can be approved by the current user
- `kanban_color` **(integer)** — Kanban Color 🔒 readonly
- `entries_count` **(integer)** — Number of Entries 🔒 readonly
