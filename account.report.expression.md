# Accounting Report Expression — `account.report.expression`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `report_line_id` **(many2one)** — Report Line ⚠️ obrigatório → `account.report.line`
- `label` **(char)** — Label ⚠️ obrigatório
- `engine` **(selection)** — Computation Engine ⚠️ obrigatório
  > Opções: `domain` (Odoo Domain), `tax_tags` (Tax Tags), `aggregation` (Aggregate Other Formulas), `account_codes` (Prefix of Account Codes), `external` (External Value), `custom` (Custom Python Function)
- `formula` **(char)** — Formula ⚠️ obrigatório
- `date_scope` **(selection)** — Date Scope ⚠️ obrigatório
  > Opções: `from_beginning` (From the very start), `from_fiscalyear` (From the start of the fiscal year), `to_beginning_of_fiscalyear` (At the beginning of the fiscal year), `to_beginning_of_period` (At the beginning of the period), `strict_range` (Strictly on the given dates), `previous_return_period` (From previous return period)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `subformula` **(char)** — Subformula
- `figure_type` **(selection)** — Figure Type
  > Opções: `monetary` (Monetary), `percentage` (Percentage), `integer` (Integer), `float` (Float), `date` (Date), `datetime` (Datetime), `boolean` (Boolean), `string` (String)
- `green_on_positive` **(boolean)** — Is Growth Good when Positive
- `blank_if_zero` **(boolean)** — Blank if Zero
  > When checked, 0 values will not show when displaying this expression's value.
- `auditable` **(boolean)** — Auditable
- `carryover_target` **(char)** — Carry Over To
  > Formula in the form line_code.expression_label. This allows setting the target of the carryover for this expression (on a _carryover_*-labeled expression), in case it is different from the parent line.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `report_line_name` **(char)** — Report Line Name 🔒 readonly
