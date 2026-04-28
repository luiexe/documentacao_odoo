# representation of an online bank account — `account.online.account`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Account Name
  > Account Name as provided by third party provider
- `online_identifier` **(char)** — Online Identifier 🔒 readonly
  > Id used to identify account by third party provider
- `balance` **(float)** — Balance 🔒 readonly
  > Balance of the account sent by the third party provider
- `available_balance` **(float)** — Available Balance 🔒 readonly
  > Available balance of the account sent by the third party provider. This is typically the balance plus/minus pending transactions.
- `account_number` **(char)** — Account Number
  > Set if third party provider has the full account number
- `account_data` **(char)** — Account Data 🔒 readonly
  > Extra information needed by third party provider
- `last_sync` **(date)** — Last Transaction Synchronized on
- `fetching_status` **(selection)** — Fetching Status
  > Opções: `planned` (Planned), `waiting` (Waiting), `processing` (Processing), `done` (Done)
- `inverse_balance_sign` **(boolean)** — Inverse Balance Sign
  > If checked, the balance sign will be inverted
- `inverse_transaction_sign` **(boolean)** — Inverse Transaction Sign
  > If checked, the transaction sign will be inverted
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `account_online_link_id` **(many2one)** — Account Online Link 🔒 readonly → `account.online.link`
- `journal_ids` **(one2many)** — Journal → `account.journal`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `currency_id` **(many2one)** — Currency → `res.currency`
