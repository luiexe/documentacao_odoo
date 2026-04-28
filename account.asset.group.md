# Asset Group — `account.asset.group`

**Ordenação padrão:** `name`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `linked_asset_ids` **(one2many)** — Related Assets → `account.asset`
- `linked_loan_ids` **(one2many)** — Related Loans → `account.loan`

## Campos Calculados (readonly)

- `count_linked_assets` **(integer)** — Count Linked Assets 🔒 readonly
- `count_linked_loans` **(integer)** — Count Linked Loans 🔒 readonly
