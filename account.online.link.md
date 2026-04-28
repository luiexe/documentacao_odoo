# Bank Connection — `account.online.link`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `state` **(selection)** — State ⚠️ obrigatório 🔒 readonly
  > Opções: `connected` (Connected), `error` (Error), `disconnected` (Not Connected)
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `last_refresh` **(datetime)** — Last Synchronization 🔒 readonly
- `connection_state_details` **(json)** — Connection State Details
- `auto_sync` **(boolean)** — Automatic synchronization
  > If possible, we will try to automatically fetch new transactions for this record                  If the automatic sync is disabled. that will be due to security policy on the bank's end. So, they have to launch the sync manually
- `has_unlinked_accounts` **(boolean)** — Has Unlinked Accounts
  > True if that connection still has accounts that are not linked to an Odoo journal
- `name` **(char)** — Name 🔒 readonly
  > Institution Name
- `client_id` **(char)** — Client 🔒 readonly
  > Represent a link for a given user towards a banking institution
- `refresh_token` **(char)** — Refresh Token 🔒 readonly
  > Token used to sign API request, Never disclose it
- `expiring_synchronization_date` **(date)** — Expiring Synchronization Date 🔒 readonly
  > Date when the consent for this connection expires
- `provider_type` **(char)** — Provider Type 🔒 readonly
  > Third Party Provider
- `renewal_contact_email` **(char)** — Connection Requests
  > Comma separated list of email addresses to send consent renewal notifications 15, 3 and 1 days before expiry
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `account_online_account_ids` **(one2many)** — Account Online Account → `account.online.account`
- `journal_ids` **(one2many)** — Journal 🔒 readonly → `account.journal`

## Campos Calculados (readonly)

- `next_refresh` **(datetime)** — Next synchronization 🔒 readonly
- `show_sync_actions` **(boolean)** — Show Sync Actions 🔒 readonly
