# Gamification Goal Definition — `gamification.goal.definition`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Goal Definition ⚠️ obrigatório
- `computation_mode` **(selection)** — Computation Mode ⚠️ obrigatório
  > Define how the goals will be computed. The result of the operation will be stored in the field 'Current'.
  > Opções: `manually` (Recorded manually), `count` (Automatic: number of records), `sum` (Automatic: sum on a field), `python` (Automatic: execute a specific Python code)
- `display_mode` **(selection)** — Displayed as ⚠️ obrigatório
  > Opções: `progress` (Progressive (using numerical values)), `boolean` (Exclusive (done or not-done))
- `domain` **(char)** — Filter Domain ⚠️ obrigatório
  > Domain for filtering records. General rule, not user depending, e.g. [('state', '=', 'done')]. The expression can contain reference to 'user' which is a browse record of the current user if not in batch mode.
- `condition` **(selection)** — Goal Performance ⚠️ obrigatório
  > A goal is considered as completed when the current value is compared to the value to reach
  > Opções: `higher` (The higher the better), `lower` (The lower the better)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(text)** — Goal Description
- `monetary` **(boolean)** — Monetary Value
  > The target and current value are defined in the company currency.
- `suffix` **(char)** — Suffix
  > The unit of the target and current values
- `batch_mode` **(boolean)** — Batch Mode
  > Evaluate the expression in batch instead of once for each user
- `batch_user_expression` **(char)** — Evaluated expression for batch mode
  > The value to compare with the distinctive field. The expression can contain reference to 'user' which is a browse record of the current user, e.g. user.id, user.partner_id.id...
- `compute_code` **(text)** — Python Code
  > Python code to be executed for each user. 'result' should contains the new current value. Evaluated user can be access through object.user_id.
- `res_id_field` **(char)** — ID Field of user
  > The field name on the user profile (res.users) containing the value for res_id for action.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `model_id` **(many2one)** — Model → `ir.model`
- `model_inherited_ids` **(many2many)** — Inherited models 🔒 readonly → `ir.model`
  > The list of models that extends the current model.
- `field_id` **(many2one)** — Field to Sum → `ir.model.fields`
- `field_date_id` **(many2one)** — Date Field → `ir.model.fields`
  > The date to use for the time period evaluated
- `batch_distinctive_field` **(many2one)** — Distinctive field for batch user → `ir.model.fields`
  > In batch mode, this indicates which field distinguishes one user from the other, e.g. user_id, partner_id...
- `action_id` **(many2one)** — Action → `ir.actions.act_window`
  > The action that will be called to update the goal value.

## Campos Calculados (readonly)

- `full_suffix` **(char)** — Full Suffix 🔒 readonly
  > The currency and suffix field
