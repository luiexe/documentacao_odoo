# Accounting Report Column — `account.report.column`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `expression_label` **(char)** — Expression Label ⚠️ obrigatório
- `figure_type` **(selection)** — Figure Type ⚠️ obrigatório
  > Opções: `monetary` (Monetary), `percentage` (Percentage), `integer` (Integer), `float` (Float), `date` (Date), `datetime` (Datetime), `boolean` (Boolean), `string` (String)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `sortable` **(boolean)** — Sortable
- `blank_if_zero` **(boolean)** — Blank if Zero
  > When checked, 0 values will not show in this column.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `report_id` **(many2one)** — Report → `account.report`
- `custom_audit_action_id` **(many2one)** — Custom Audit Action → `ir.actions.act_window`
