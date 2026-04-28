# Mailing Contact — `mailing.contact`

**Ordenação padrão:** `name ASC, id DESC`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `properties` **(properties)** — Properties
- `email_normalized` **(char)** — Normalized Email 🔒 readonly
  > This field is used to search on email address as the primary email field can contain more than strictly an email address.
- `message_bounce` **(integer)** — Bounce
  > Counter of the number of bounced emails for this contact
- `name` **(char)** — Name
- `first_name` **(char)** — First Name
- `last_name` **(char)** — Last Name
- `company_name` **(char)** — Company Name
- `email` **(char)** — Email
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `x_studio_cupom_de_inscricao_na_newsletter` **(char)** — Cupom de inscrição na newsletter 🔒 readonly

## Relacionamentos

- `properties_base_definition_id` **(many2one)** — Properties Base Definition 🔒 readonly → `properties.base.definition`
- `list_ids` **(many2many)** — Mailing Lists → `mailing.list`
- `subscription_ids` **(one2many)** — Subscription Information → `mailing.subscription`
- `country_id` **(many2one)** — Country → `res.country`
- `tag_ids` **(many2many)** — Tags → `res.partner.category`

## Campos Calculados (readonly)

- `is_blacklisted` **(boolean)** — Blacklist 🔒 readonly
  > If the email address is on the blacklist, the contact won't receive mass mailing anymore, from any list
- `opt_out` **(boolean)** — Opt Out 🔒 readonly
  > Opt out flag for a specific mailing list. This field should not be used in a view without a unique and active mailing list context.
