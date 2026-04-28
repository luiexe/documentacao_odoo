# Secure Journal Entries — `account.secure.entries.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `hash_date` **(date)** — Hash All Entries ⚠️ obrigatório
  > The selected Date

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `unreconciled_bank_statement_line_ids` **(many2many)** — Unreconciled Bank Statement Line 🔒 readonly → `account.bank.statement.line`
  > All unreconciled bank statement lines before the selected date.
- `not_hashable_unlocked_move_ids` **(many2many)** — Not Hashable Unlocked Move 🔒 readonly → `account.move`
  > All unhashable moves before the selected date that are not protected by the Hard Lock Date
- `move_to_hash_ids` **(many2many)** — Move To Hash 🔒 readonly → `account.move`
  > All moves that will be hashed

## Campos Calculados (readonly)

- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `chains_to_hash_with_gaps` **(json)** — Chains To Hash With Gaps 🔒 readonly
- `max_hash_date` **(date)** — Max Hash Date 🔒 readonly
  > Highest Date such that all posted journal entries prior to (including) the date are secured. Only journal entries after the hard lock date are considered.
- `warnings` **(json)** — Warnings 🔒 readonly
