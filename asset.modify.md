# Modify Asset — `asset.modify`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `asset_id` **(many2one)** — Asset ⚠️ obrigatório → `account.asset`
  > The asset to be modified by this wizard
- `method_number` **(integer)** — Duration ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(text)** — Note
- `method_period` **(selection)** — Number of Months in a Period
  > The amount of time between two depreciations
  > Opções: `1` (Months), `12` (Years)
- `value_residual` **(monetary)** — Depreciable Amount
  > New residual amount for the asset
- `salvage_value` **(monetary)** — Not Depreciable Amount
  > New salvage amount for the asset
- `date` **(date)** — Date
- `modify_action` **(selection)** — Action
  > Opções: `dispose` (Dispose), `sell` (Sell), `modify` (Re-evaluate), `pause` (Pause)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `account_asset_id` **(many2one)** — Gross Increase Account → `account.account`
- `account_asset_counterpart_id` **(many2one)** — Asset Counterpart Account → `account.account`
- `account_depreciation_id` **(many2one)** — Depreciation Account → `account.account`
- `account_depreciation_expense_id` **(many2one)** — Expense Account → `account.account`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `invoice_ids` **(many2many)** — Customer Invoice → `account.move`
  > The disposal invoice is needed in order to generate the closing journal entry.
- `invoice_line_ids` **(many2many)** — Invoice Line → `account.move.line`
  > There are multiple lines that could be the related to this asset
- `gain_account_id` **(many2one)** — Gain Account → `account.account`
  > Account used to write the journal item in case of gain
- `loss_account_id` **(many2one)** — Loss Account → `account.account`
  > Account used to write the journal item in case of loss

## Campos Calculados (readonly)

- `select_invoice_line_id` **(boolean)** — Select Invoice Line 🔒 readonly
- `gain_value` **(boolean)** — Gain Value 🔒 readonly
- `informational_text` **(html)** — Informational Text 🔒 readonly
- `gain_or_loss` **(selection)** — Gain Or Loss 🔒 readonly
  > Opções: `gain` (Gain), `loss` (Loss), `no` (No)
