# Account merge wizard — `account.merge.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `is_group_by_name` **(boolean)** — Group by name?
  > Tick this checkbox if you want accounts to be grouped by name for merging.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `account_ids` **(many2many)** — Account → `account.account`
- `wizard_line_ids` **(one2many)** — Wizard Line → `account.merge.wizard.line`

## Campos Calculados (readonly)

- `disable_merge_button` **(boolean)** — Disable Merge Button 🔒 readonly
