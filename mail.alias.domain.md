# Email Domain — `mail.alias.domain`

**Ordenação padrão:** `sequence ASC, id ASC`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
  > Email domain e.g. 'example.com' in 'odoo@example.com'
- `bounce_alias` **(char)** — Bounce Alias ⚠️ obrigatório
  > Local-part of email used for Return-Path used when emails bounce e.g. 'bounce' in 'bounce@example.com'
- `catchall_alias` **(char)** — Catchall Alias ⚠️ obrigatório
  > Local-part of email used for Reply-To to catch answers e.g. 'catchall' in 'catchall@example.com'

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `default_from` **(char)** — Default From Alias
  > Default from when it does not match outgoing server filters. Can be either a local-part e.g. 'notifications' either a complete email address e.g. 'notifications@example.com' to override all outgoing emails.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_ids` **(one2many)** — Companies → `res.company`
  > Companies using this domain as default for sending mails

## Campos Calculados (readonly)

- `bounce_email` **(char)** — Bounce Email 🔒 readonly
- `catchall_email` **(char)** — Catchall Email 🔒 readonly
- `default_from_email` **(char)** — Default From 🔒 readonly
