# Account reconciliation wizard — `account.reconcile.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `move_line_ids` **(many2many)** — Move lines to reconcile ⚠️ obrigatório → `account.move.line`
- `journal_id` **(many2one)** — Journal ⚠️ obrigatório → `account.journal`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `edit_mode_amount_currency` **(monetary)** — Edit mode amount
- `allow_partials` **(boolean)** — Allow partials
- `date` **(date)** — Date
- `label` **(char)** — Label
- `to_check` **(boolean)** — To Check
  > Check if you are not certain of all the information of the counterpart.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `reco_account_id` **(many2one)** — Reconcile Account 🔒 readonly → `account.account`
- `company_currency_id` **(many2one)** — Company currency 🔒 readonly → `res.currency`
- `reco_currency_id` **(many2one)** — Currency to use for reconciliation 🔒 readonly → `res.currency`
- `edit_mode_reco_currency_id` **(many2one)** — Edit Mode Reco Currency 🔒 readonly → `res.currency`
- `account_id` **(many2one)** — Account → `account.account`
- `to_partner_id` **(many2one)** — Partner → `res.partner`
- `tax_id` **(many2one)** — Tax → `account.tax`
- `transfer_from_account_id` **(many2one)** — Account Transfer From 🔒 readonly → `account.account`
- `reco_model_id` **(many2one)** — Reconciliation model → `account.reconcile.model`
- `reco_model_autocomplete_ids` **(many2many)** — All reconciliation models 🔒 readonly → `account.reconcile.model`

## Campos Calculados (readonly)

- `amount` **(monetary)** — Amount in company currency 🔒 readonly
- `amount_currency` **(monetary)** — Amount 🔒 readonly
- `edit_mode_amount` **(monetary)** — Edit Mode Amount 🔒 readonly
- `edit_mode` **(boolean)** — Edit Mode 🔒 readonly
- `single_currency_mode` **(boolean)** — Single Currency Mode 🔒 readonly
- `force_partials` **(boolean)** — Force Partials 🔒 readonly
- `display_allow_partials` **(boolean)** — Display Allow Partials 🔒 readonly
- `is_rec_pay_account` **(boolean)** — Is Rec Pay Account 🔒 readonly
- `is_write_off_required` **(boolean)** — Is a write-off move required to reconcile 🔒 readonly
- `is_transfer_required` **(boolean)** — Is an account transfer required 🔒 readonly
- `transfer_warning_message` **(char)** — Is an account transfer required to reconcile 🔒 readonly
- `lock_date_violated_warning_message` **(char)** — Is the date violating the lock date of moves 🔒 readonly
