# Currency — `res.currency`

**Ordenação padrão:** `active desc, name`

---

## Campos Obrigatórios

- `name` **(char)** — Currency ⚠️ obrigatório
  > Currency Code (ISO 4217)
- `symbol` **(char)** — Symbol ⚠️ obrigatório
  > Currency sign, to be used when printing amounts.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `iso_numeric` **(integer)** — Currency numeric code.
  > Currency Numeric Code (ISO 4217).
- `full_name` **(char)** — Name
- `rounding` **(float)** — Rounding Factor
  > Amounts in this currency are rounded off to the nearest multiple of the rounding factor.
- `decimal_places` **(integer)** — Decimal Places 🔒 readonly
  > Decimal places taken into account for operations on amounts in this currency. It is determined by the rounding factor.
- `active` **(boolean)** — Active
- `position` **(selection)** — Symbol Position
  > Determines where the currency symbol should be placed after or before the amount.
  > Opções: `after` (After Amount), `before` (Before Amount)
- `currency_unit_label` **(char)** — Currency Unit
- `currency_subunit_label` **(char)** — Currency Subunit
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `fiscal_country_codes` **(char)** — Fiscal Country Codes

## Relacionamentos

- `rate_ids` **(one2many)** — Rates → `res.currency.rate`

## Campos Calculados (readonly)

- `rate` **(float)** — Current Rate 🔒 readonly
  > The rate of the currency to the currency of rate 1.
- `inverse_rate` **(float)** — Inverse Rate 🔒 readonly
  > The currency of rate 1 to the rate of the currency.
- `rate_string` **(char)** — Rate String 🔒 readonly
- `date` **(date)** — Date 🔒 readonly
- `is_current_company_currency` **(boolean)** — Is Current Company Currency 🔒 readonly
- `display_rounding_warning` **(boolean)** — Display Rounding Warning 🔒 readonly
  > The warning informs a rounding factor change might be dangerous on res.currency's form view.
