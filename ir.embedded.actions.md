# Embedded Actions — `ir.embedded.actions`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `parent_action_id` **(many2one)** — Parent Action ⚠️ obrigatório → `ir.actions.act_window`
- `parent_res_model` **(char)** — Active Parent Model ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `sequence` **(integer)** — Sequence
- `parent_res_id` **(integer)** — Active Parent Id
- `python_method` **(char)** — Python Method
  > Python method returning an action
- `default_view_mode` **(char)** — Default View
  > Default view (if none, default view of the action is taken)
- `domain` **(char)** — Domain
  > Domain applied to the active id of the parent model
- `context` **(char)** — Context
  > Context dictionary as Python expression, empty by default (Default: {})
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `action_id` **(many2one)** — Action → `ir.actions.actions`
- `user_id` **(many2one)** — User → `res.users`
  > User specific embedded action. If empty, shared embedded action
- `filter_ids` **(one2many)** — Filter → `ir.filters`
  > Default filter of the embedded action (if none, no filters)
- `groups_ids` **(many2many)** — Groups → `res.groups`
  > Groups that can execute the embedded action. Leave empty to allow everybody.

## Campos Calculados (readonly)

- `is_deletable` **(boolean)** — Is Deletable 🔒 readonly
- `is_visible` **(boolean)** — Embedded visibility 🔒 readonly
  > Computed field to check if the record should be visible according to the domain
