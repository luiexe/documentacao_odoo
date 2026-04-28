# Mail Blacklist — `mail.blacklist`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `email` **(char)** — Email Address ⚠️ obrigatório
  > This field is case insensitive.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `opt_out_reason_id` **(many2one)** — Opt-out Reason → `mailing.subscription.optout`
