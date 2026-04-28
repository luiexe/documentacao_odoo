# Email Aliases Mixin (light) — `mail.alias.mixin.optional`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `alias_name` **(char)** — Alias Name
  > The name of the email alias, e.g. 'jobs' if you want to catch emails for <jobs@example.odoo.com>

## Relacionamentos

- `alias_id` **(many2one)** — Alias → `mail.alias`
- `alias_domain_id` **(many2one)** — Alias Domain → `mail.alias.domain`

## Campos Calculados (readonly)

- `alias_domain` **(char)** — Alias Domain Name 🔒 readonly
  > Email domain e.g. 'example.com' in 'odoo@example.com'
- `alias_defaults` **(text)** — Default Values 🔒 readonly
  > A Python dictionary that will be evaluated to provide default values when creating new records for this alias.
- `alias_email` **(char)** — Email Alias 🔒 readonly
