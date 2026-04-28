# Mail Blacklist mixin — `mail.thread.blacklist`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `email_normalized` **(char)** — Normalized Email 🔒 readonly
  > This field is used to search on email address as the primary email field can contain more than strictly an email address.
- `message_bounce` **(integer)** — Bounce
  > Counter of the number of bounced emails for this contact

## Campos Calculados (readonly)

- `is_blacklisted` **(boolean)** — Blacklist 🔒 readonly
  > If the email address is on the blacklist, the contact won't receive mass mailing anymore, from any list
