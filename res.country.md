# Country — `res.country`

**Ordenação padrão:** `name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Country Name ⚠️ obrigatório
- `code` **(char)** — Country Code ⚠️ obrigatório
  > The ISO country code in two chars.  You can use this field for quick search.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `address_format` **(text)** — Layout in Reports
  > Display format to use for addresses belonging to this country.  You can use python-style string pattern with all the fields of the address (for example, use '%(street)s' to display the field 'street') plus %(state_name)s: the name of the state %(state_code)s: the code of the state %(country_name)s: the name of the country %(country_code)s: the code of the country
- `phone_code` **(integer)** — Country Calling Code
- `name_position` **(selection)** — Customer Name Position
  > Determines where the customer/company name should be placed, i.e. after or before the address.
  > Opções: `before` (Before Address), `after` (After Address)
- `vat_label` **(char)** — Vat Label
  > Use this field if you want to change vat label.
- `state_required` **(boolean)** — State Required
- `zip_required` **(boolean)** — Zip Required
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `enforce_cities` **(boolean)** — Enforce Cities
  > Check this box to ensure every address created in that country has a 'City' chosen in the list of the country's cities.
- `l10n_br_edi_code` **(char)** — BR Country Code 🔒 readonly
  > Brazil: Country Code used in NF-e

## Relacionamentos

- `address_view_id` **(many2one)** — Input View → `ir.ui.view`
  > Use this field if you want to replace the usual way to encode a complete address. Note that the address_format field is used to modify the way to display addresses (in reports for example), while this field is used to modify the input form for addresses.
- `currency_id` **(many2one)** — Currency → `res.currency`
- `country_group_ids` **(many2many)** — Country Groups → `res.country.group`
- `state_ids` **(one2many)** — States → `res.country.state`

## Campos Calculados (readonly)

- `image_url` **(char)** — Flag 🔒 readonly
  > Url of static flag image
- `country_group_codes` **(json)** — Country Group Codes 🔒 readonly
- `is_mercado_pago_supported_country` **(boolean)** — Is Mercado Pago Supported Country 🔒 readonly
- `is_stripe_supported_country` **(boolean)** — Is Stripe Supported Country 🔒 readonly
- `has_foreign_fiscal_position` **(boolean)** — Has Foreign Fiscal Position 🔒 readonly
