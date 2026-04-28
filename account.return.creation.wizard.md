# Return creation wizard — `account.return.creation.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `return_type_id` **(many2one)** — Return Type ⚠️ obrigatório → `account.return.type`
- `date_from` **(date)** — Date From ⚠️ obrigatório
- `date_to` **(date)** — Date To ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `category` **(selection)** — Category
  > Opções: `account_return` (Tax Return), `audit` (Audit)
- `regulatory_compliance` **(boolean)** — Regulatory compliance
- `treasury_financing` **(boolean)** — Treasury and financing
- `purchases` **(boolean)** — Purchases
- `operating_expenses` **(boolean)** — Operating expenses
- `sales` **(boolean)** — Sales
- `inventory` **(boolean)** — Inventory
- `fixed_assets` **(boolean)** — Fixed assets
- `payroll` **(boolean)** — Payroll
- `government` **(boolean)** — Government
- `equity` **(boolean)** — Equity
- `other` **(boolean)** — Others
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `available_return_type_ids` **(many2many)** — Available Return Type 🔒 readonly → `account.return.type`

## Campos Calculados (readonly)

- `show_warning_wrong_dates` **(boolean)** — Show Warning Wrong Dates 🔒 readonly
- `show_warning_existing_return` **(boolean)** — Show Warning Existing Return 🔒 readonly
- `show_warning_overlap` **(boolean)** — Show Warning Overlap 🔒 readonly
- `is_create_disabled` **(boolean)** — Is Create Disabled 🔒 readonly
