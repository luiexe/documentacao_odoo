# Link a bank account to the selected journal — `account.bank.selection`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `account_online_link_id` **(many2one)** — Account Online Link → `account.online.link`
- `account_online_account_ids` **(one2many)** — Account Online Account 🔒 readonly → `account.online.account`
- `selected_account` **(many2one)** — Selected Account → `account.online.account`

## Campos Calculados (readonly)

- `institution_name` **(char)** — Name 🔒 readonly
  > Institution Name
