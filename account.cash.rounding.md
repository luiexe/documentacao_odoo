# Account Cash Rounding — `account.cash.rounding`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `rounding` **(float)** — Rounding Precision ⚠️ obrigatório
  > Represent the non-zero value smallest coinage (for example, 0.05).
- `strategy` **(selection)** — Rounding Strategy ⚠️ obrigatório
  > Specify which way will be used to round the invoice amount to the rounding precision
  > Opções: `biggest_tax` (Modify tax amount), `add_invoice_line` (Add a rounding line)
- `rounding_method` **(selection)** — Rounding Method ⚠️ obrigatório
  > The tie-breaking rule used for float rounding operations
  > Opções: `UP` (Up), `DOWN` (Down), `HALF-UP` (Nearest)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `profit_account_id` **(many2one)** — Profit Account → `account.account`
- `loss_account_id` **(many2one)** — Loss Account → `account.account`
