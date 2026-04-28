# Engineering Change Order (ECO) — `mrp.eco`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Reference ⚠️ obrigatório
- `type_id` **(many2one)** — Type ⚠️ obrigatório → `mrp.eco.type`
- `state` **(selection)** — Status ⚠️ obrigatório 🔒 readonly
  > Opções: `confirmed` (To Do), `progress` (In Progress), `rebase` (Rebase), `conflict` (Conflict), `done` (Done)
- `type` **(selection)** — Apply on ⚠️ obrigatório
  > Opções: `bom` (Bill of Materials), `product` (Product Only)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `email_cc` **(char)** — Email cc
- `priority` **(selection)** — Priority
  > Opções: `0` (Normal), `1` (High)
- `note` **(html)** — Note
- `effectivity` **(selection)** — Effective
  > Date on which the changes should be applied. For reference only.
  > Opções: `asap` (As soon as possible), `date` (At Date)
- `effectivity_date` **(datetime)** — Effective Date
  > For reference only.
- `kanban_state` **(selection)** — Kanban State
  > Opções: `normal` (In Progress), `done` (Approved), `blocked` (Blocked)
- `new_bom_revision` **(integer)** — BoM Revision
- `will_update_version` **(boolean)** — Update Version
  > If unchecked, the version of the product/BoM will remain unchanged once the ECO is applied
- `color` **(integer)** — Color
- `active` **(boolean)** — Active
  > If the active field is set to False, it will allow you to hide the engineering change order without removing it.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — Responsible → `res.users`
- `stage_id` **(many2one)** — Stage → `mrp.eco.stage`
- `company_id` **(many2one)** — Company → `res.company`
- `tag_ids` **(many2many)** — Tags → `mrp.eco.tag`
- `approval_ids` **(one2many)** — Approvals → `mrp.eco.approval`
  > Approvals by stage
- `product_tmpl_id` **(many2one)** — Product → `product.template`
- `production_id` **(many2one)** — Manufacturing Orders 🔒 readonly → `mrp.production`
- `bom_id` **(many2one)** — Bill of Materials → `mrp.bom`
- `new_bom_id` **(many2one)** — New Bill of Materials → `mrp.bom`
- `bom_change_ids` **(one2many)** — ECO BoM Changes 🔒 readonly → `mrp.eco.bom.change`
  > Difference between old BoM and new BoM revision
- `bom_change_ids_on_line` **(one2many)** — ECO BoM Changes - Component → `mrp.eco.bom.change`
- `bom_change_ids_on_byproduct` **(one2many)** — ECO BoM Changes - By-Product → `mrp.eco.bom.change`
- `bom_rebase_ids` **(one2many)** — BoM Rebase → `mrp.eco.bom.change`
- `routing_change_ids` **(one2many)** — ECO Routing Changes 🔒 readonly → `mrp.eco.routing.change`
  > Difference between old operation and new operation revision
- `document_ids` **(one2many)** — Attachments → `product.document`
- `displayed_image_id` **(many2one)** — Displayed Image → `product.document`
- `displayed_image_attachment_id` **(many2one)** — Related attachment → `ir.attachment`
- `current_bom_id` **(many2one)** — New Bom → `mrp.bom`
- `previous_change_ids` **(one2many)** — Previous ECO Changes 🔒 readonly → `mrp.eco.bom.change`
- `routing_change_ids_on_operation` **(one2many)** — ECO Routing Changes - Operation → `mrp.eco.routing.change`
- `routing_change_ids_on_quality_point` **(one2many)** — ECO Routing Changes - Quality Point → `mrp.eco.routing.change`

## Campos Calculados (readonly)

- `user_can_approve` **(boolean)** — Can Approve 🔒 readonly
  > Technical field to check if approval by current user is required
- `user_can_reject` **(boolean)** — Can Reject 🔒 readonly
  > Technical field to check if reject by current user is possible
- `legend_blocked` **(char)** — Kanban Blocked Explanation 🔒 readonly
  > Override the default value displayed for the blocked state for kanban selection, when the ECO is in that stage.
- `legend_done` **(char)** — Kanban Valid Explanation 🔒 readonly
  > Override the default value displayed for the done state for kanban selection, when the ECO is in that stage.
- `legend_normal` **(char)** — Kanban Ongoing Explanation 🔒 readonly
  > Override the default value displayed for the normal state for kanban selection, when the ECO is in that stage.
- `kanban_state_label` **(char)** — Kanban State Label 🔒 readonly
- `allow_change_kanban_state` **(boolean)** — Allow Change Kanban State 🔒 readonly
- `allow_change_stage` **(boolean)** — Allow Change Stage 🔒 readonly
- `allow_apply_change` **(boolean)** — Show Apply Change 🔒 readonly
- `document_count` **(integer)** — # Attachments 🔒 readonly
