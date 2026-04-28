# Mailing List — `mailing.list`

**Ordenação padrão:** `create_date DESC`

---

## Campos Obrigatórios

- `name` **(char)** — Mailing List ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `is_public` **(boolean)** — Show In Preferences
  > The mailing list can be accessible by recipients in the subscription management page to allow them to update their preferences.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `contact_ids` **(many2many)** — Mailing Lists → `mailing.contact`
- `mailing_ids` **(many2many)** — Mass Mailings → `mailing.mailing`
- `subscription_ids` **(one2many)** — Subscription Information → `mailing.subscription`

## Campos Calculados (readonly)

- `contact_count` **(integer)** — Number of Contacts 🔒 readonly
- `contact_count_email` **(integer)** — Number of Emails 🔒 readonly
- `contact_count_opt_out` **(integer)** — Number of Opted-out 🔒 readonly
- `contact_pct_opt_out` **(float)** — Percentage of Opted-out 🔒 readonly
- `contact_count_blacklisted` **(integer)** — Number of Blacklisted 🔒 readonly
- `contact_pct_blacklisted` **(float)** — Percentage of Blacklisted 🔒 readonly
- `contact_pct_bounce` **(float)** — Percentage of Bouncing 🔒 readonly
- `mailing_count` **(integer)** — Number of Mailing 🔒 readonly
