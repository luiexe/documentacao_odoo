# Mailing List Subscription — `mailing.subscription`

**Ordenação padrão:** `list_id DESC, contact_id DESC`

---

## Campos Obrigatórios

- `contact_id` **(many2one)** — Contact ⚠️ obrigatório → `mailing.contact`
- `list_id` **(many2one)** — Mailing List ⚠️ obrigatório → `mailing.list`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `opt_out` **(boolean)** — Opt Out
  > The contact has chosen not to receive mails anymore from this list
- `opt_out_datetime` **(datetime)** — Unsubscription Date
- `message_bounce` **(integer)** — Bounce
  > Counter of the number of bounced emails for this contact
- `is_blacklisted` **(boolean)** — Blacklist
  > If the email address is on the blacklist, the contact won't receive mass mailing anymore, from any list
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `opt_out_reason_id` **(many2one)** — Reason → `mailing.subscription.optout`
