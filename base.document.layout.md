# Company Document Layout — `base.document.layout`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `logo` **(binary)** — Company Logo
- `report_header` **(html)** — Company Tagline
  > Company tagline, which is included in a printed document's header or footer (depending on the selected layout).
- `report_footer` **(html)** — Report Footer
  > Footer text displayed at the bottom of all reports.
- `company_details` **(html)** — Company Details
  > Header text displayed at the top of all reports.
- `font` **(selection)** — Font
  > Opções: `Lato` (Lato), `Roboto` (Roboto), `Open_Sans` (Open Sans), `Montserrat` (Montserrat), `Oswald` (Oswald), `Raleway` (Raleway), `Tajawal` (Tajawal), `Fira_Mono` (Fira Mono)
- `primary_color` **(char)** — Primary Color
- `secondary_color` **(char)** — Secondary Color
- `custom_colors` **(boolean)** — Custom Colors
- `layout_background` **(selection)** — Layout Background
  > Opções: `Blank` (Blank), `Demo logo` (Demo logo), `Custom` (Custom)
- `layout_background_image` **(binary)** — Background Image
- `vat` **(char)** — Tax ID
  > Identification Number for selected type
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `from_invoice` **(boolean)** — From Invoice
- `qr_code` **(boolean)** — Display QR-code on invoices
- `account_number` **(char)** — Account Number

## Relacionamentos

- `paperformat_id` **(many2one)** — Paper format → `report.paperformat`
- `external_report_layout_id` **(many2one)** — Document Template → `ir.ui.view`
- `report_layout_id` **(many2one)** — Report Layout → `report.layout`
- `partner_id` **(many2one)** — Partner 🔒 readonly → `res.partner`
- `country_id` **(many2one)** — Country 🔒 readonly → `res.country`

## Campos Calculados (readonly)

- `preview_logo` **(binary)** — Preview logo 🔒 readonly
- `is_company_details_empty` **(boolean)** — Is Company Details Empty 🔒 readonly
- `logo_primary_color` **(char)** — Logo Primary Color 🔒 readonly
- `logo_secondary_color` **(char)** — Logo Secondary Color 🔒 readonly
- `preview` **(html)** — Preview 🔒 readonly
- `phone` **(char)** — Phone 🔒 readonly
- `email` **(char)** — Email 🔒 readonly
- `website` **(char)** — Website Link 🔒 readonly
- `name` **(char)** — Company Name 🔒 readonly
