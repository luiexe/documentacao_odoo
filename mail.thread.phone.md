# Phone Blacklist Mixin — `mail.thread.phone`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `phone_sanitized` **(char)** — Sanitized Number 🔒 readonly
  > Field used to store sanitized phone number. Helps speeding up searches and comparisons.
- `phone_mobile_search` **(char)** — Phone Number

## Campos Calculados (readonly)

- `phone_sanitized_blacklisted` **(boolean)** — Phone Blacklisted 🔒 readonly
  > If the sanitized phone number is on the blacklist, the contact won't receive mass mailing sms anymore, from any list
- `phone_blacklisted` **(boolean)** — Blacklisted Phone is Phone 🔒 readonly
  > Indicates if a blacklisted sanitized phone number is a phone number. Helps distinguish which number is blacklisted             when there is both a mobile and phone field in a model.
