# Accounting Report Line — `account.report.line`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `report_id` **(many2one)** — Parent Report ⚠️ obrigatório → `account.report`
- `hierarchy_level` **(integer)** — Level ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `groupby` **(char)** — Group By
  > Comma-separated list of fields from account.move.line (Journal Item). When set, this line will generate sublines grouped by those keys.
- `user_groupby` **(char)** — User Group By
  > Comma-separated list of fields from account.move.line (Journal Item). When set, this line will generate sublines grouped by those keys.
- `sequence` **(integer)** — Sequence
- `code` **(char)** — Code
  > Unique identifier for this line.
- `foldable` **(boolean)** — Foldable
  > By default, we always unfold the lines that can be. If this is checked, the line won't be unfolded by default, and a folding button will be displayed.
- `print_on_new_page` **(boolean)** — Print On New Page
  > When checked this line and everything after it will be printed on a new page.
- `hide_if_zero` **(boolean)** — Hide if Zero
  > This line and its children will be hidden when all of their columns are 0.
- `domain_formula` **(char)** — Domain Formula Shortcut
  > Internal field to shorten expression_ids creation for the domain engine
- `account_codes_formula` **(char)** — Account Codes Formula Shortcut
  > Internal field to shorten expression_ids creation for the account_codes engine
- `aggregation_formula` **(char)** — Aggregation Formula Shortcut
  > Internal field to shorten expression_ids creation for the aggregation engine
- `external_formula` **(char)** — External Formula Shortcut
  > Internal field to shorten expression_ids creation for the external engine
- `horizontal_split_side` **(selection)** — Horizontal Split Side
  > Opções: `left` (Left), `right` (Right)
- `tax_tags_formula` **(char)** — Tax Tags Formula Shortcut
  > Internal field to shorten expression_ids creation for the tax_tags engine
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `expression_ids` **(one2many)** — Expressions → `account.report.expression`
- `parent_id` **(many2one)** — Parent Line → `account.report.line`
- `children_ids` **(one2many)** — Child Lines → `account.report.line`
- `action_id` **(many2one)** — Action → `ir.actions.actions`
  > Setting this field will turn the line into a link, executing the action when clicked.

## Campos Calculados (readonly)

- `display_custom_groupby_warning` **(boolean)** — Display Custom Groupby Warning 🔒 readonly
