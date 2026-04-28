# Tax — `account.tax`

**Ordenação padrão:** `sequence,id`

---

## Campos Obrigatórios

- `name` **(char)** — Tax Name ⚠️ obrigatório
- `type_tax_use` **(selection)** — Tax Type ⚠️ obrigatório
  > Determines where the tax is selectable. Note: 'None' means a tax can't be used by itself, however it can still be used in a group. 'adjustment' is used to perform tax adjustment.
  > Opções: `sale` (Sales), `purchase` (Purchases), `none` (None)
- `amount_type` **(selection)** — Tax Computation ⚠️ obrigatório
  >      - Group of Taxes: The tax is a set of sub taxes.     - Fixed: The tax amount stays the same whatever the price.     - Percentage: The tax amount is a % of the price:         e.g 100 * (1 + 10%) = 110 (not price included)         e.g 110 / (1 + 10%) = 100 (price included)     - Percentage Tax Included: The tax amount is a division of the price:         e.g 180 / (1 - 10%) = 200 (not price included)         e.g 200 * (1 - 10%) = 180 (price included)         
  > Opções: `group` (Group of Taxes), `fixed` (Fixed), `percent` (Percentage), `division` (Percentage Tax Included)
- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `sequence` **(integer)** — Sequence ⚠️ obrigatório
  > The sequence field is used to define order in which the tax lines are applied.
- `amount` **(float)** — Amount ⚠️ obrigatório
- `tax_group_id` **(many2one)** — Tax Group ⚠️ obrigatório → `account.tax.group`
- `country_id` **(many2one)** — Country ⚠️ obrigatório → `res.country`
  > The country for which this tax is applicable.
- `base_reduction` **(float)** — Redution ⚠️ obrigatório
  > Um percentual decimal em % entre 0-1.
- `amount_mva` **(float)** — MVA Percent ⚠️ obrigatório
  > Um percentual decimal em % entre 0-1.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `tax_scope` **(selection)** — Tax Scope
  > Opções: `service` (Services), `consu` (Goods)
- `is_domestic` **(boolean)** — Is Domestic 🔒 readonly
- `active` **(boolean)** — Active
  > Set active to false to hide the tax without removing it.
- `description` **(html)** — Description
- `invoice_label` **(char)** — Label on Invoices
- `price_include_override` **(selection)** — Included in Price
  > Overrides the Company's default on whether the price you use on the product and invoices includes this tax.
  > Opções: `tax_included` (Tax Included), `tax_excluded` (Tax Excluded)
- `include_base_amount` **(boolean)** — Affect Base of Subsequent Taxes
  > If set, taxes with a higher sequence than this one will be affected by it, provided they accept it.
- `is_base_affected` **(boolean)** — Base Affected by Previous Taxes
  > If set, taxes with a lower sequence might affect this one, provided they try to do it.
- `analytic` **(boolean)** — Include in Analytic Cost
  > If set, the amount computed by this tax will be assigned to the same analytic account as the invoice line (if any)
- `tax_exigibility` **(selection)** — Tax Exigibility
  > Based on Invoice: the tax is due as soon as the invoice is validated. Based on Payment: the tax is due as soon as the payment of the invoice is received.
  > Opções: `on_invoice` (Based on Invoice), `on_payment` (Based on Payment)
- `invoice_legal_notes` **(html)** — Legal Notes
  > Legal mentions that have to be printed on the invoices.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `ubl_cii_tax_category_code` **(selection)** — Tax Category Code
  > The VAT category code used for electronic invoicing purposes.
  > Opções: `AE` (AE - Vat Reverse Charge), `E` (E - Exempt from Tax), `S` (S - Standard rate), `Z` (Z - Zero rated goods), `G` (G - Free export item, VAT not charged), `O` (O - Services outside scope of tax), `K` (K - VAT exempt for EEA intra-community supply of goods and services), `L` (L - Canary Islands general indirect tax), `M` (M - Tax for production, services and importation in Ceuta and Melilla), `B` (B - Transferred (VAT), In Italy)
- `ubl_cii_tax_exemption_reason_code` **(selection)** — Tax Exemption Reason Code
  > The reason why the amount is exempted from VAT or why no VAT is being charged, used for electronic invoicing purposes.
  > Opções: `VATEX-EU-79-C` (VATEX-EU-79-C - Exempt based on article 79, point c of Council Directive 2006/112/EC), `VATEX-EU-132` (VATEX-EU-132 - Exempt based on article 132 of Council Directive 2006/112/EC), `VATEX-EU-132-1A` (VATEX-EU-132-1A - Exempt based on article 132, section 1 (a) of Council Directive 2006/112/EC), `VATEX-EU-132-1B` (VATEX-EU-132-1B - Exempt based on article 132, section 1 (b) of Council Directive 2006/112/EC), `VATEX-EU-132-1C` (VATEX-EU-132-1C - Exempt based on article 132, section 1 (c) of Council Directive 2006/112/EC), `VATEX-EU-132-1D` (VATEX-EU-132-1D - Exempt based on article 132, section 1 (d) of Council Directive 2006/112/EC), `VATEX-EU-132-1E` (VATEX-EU-132-1E - Exempt based on article 132, section 1 (e) of Council Directive 2006/112/EC), `VATEX-EU-132-1F` (VATEX-EU-132-1F - Exempt based on article 132, section 1 (f) of Council Directive 2006/112/EC), `VATEX-EU-132-1G` (VATEX-EU-132-1G - Exempt based on article 132, section 1 (g) of Council Directive 2006/112/EC), `VATEX-EU-132-1H` (VATEX-EU-132-1H - Exempt based on article 132, section 1 (h) of Council Directive 2006/112/EC), `VATEX-EU-132-1I` (VATEX-EU-132-1I - Exempt based on article 132, section 1 (i) of Council Directive 2006/112/EC), `VATEX-EU-132-1J` (VATEX-EU-132-1J - Exempt based on article 132, section 1 (j) of Council Directive 2006/112/EC), `VATEX-EU-132-1K` (VATEX-EU-132-1K - Exempt based on article 132, section 1 (k) of Council Directive 2006/112/EC), `VATEX-EU-132-1L` (VATEX-EU-132-1L - Exempt based on article 132, section 1 (l) of Council Directive 2006/112/EC), `VATEX-EU-132-1M` (VATEX-EU-132-1M - Exempt based on article 132, section 1 (m) of Council Directive 2006/112/EC), `VATEX-EU-132-1N` (VATEX-EU-132-1N - Exempt based on article 132, section 1 (n) of Council Directive 2006/112/EC), `VATEX-EU-132-1O` (VATEX-EU-132-1O - Exempt based on article 132, section 1 (o) of Council Directive 2006/112/EC), `VATEX-EU-132-1P` (VATEX-EU-132-1P - Exempt based on article 132, section 1 (p) of Council Directive 2006/112/EC), `VATEX-EU-132-1Q` (VATEX-EU-132-1Q - Exempt based on article 132, section 1 (q) of Council Directive 2006/112/EC), `VATEX-EU-135-1` (VATEX-EU-135-1 - Exempt based on article 135, section 1 of Council Directive 2006/112/EC), `VATEX-EU-143` (VATEX-EU-143 - Exempt based on article 143 of Council Directive 2006/112/EC), `VATEX-EU-143-1A` (VATEX-EU-143-1A - Exempt based on article 143, section 1 (a) of Council Directive 2006/112/EC), `VATEX-EU-143-1B` (VATEX-EU-143-1B - Exempt based on article 143, section 1 (b) of Council Directive 2006/112/EC), `VATEX-EU-143-1C` (VATEX-EU-143-1C - Exempt based on article 143, section 1 (c) of Council Directive 2006/112/EC), `VATEX-EU-143-1D` (VATEX-EU-143-1D - Exempt based on article 143, section 1 (d) of Council Directive 2006/112/EC), `VATEX-EU-143-1E` (VATEX-EU-143-1E - Exempt based on article 143, section 1 (e) of Council Directive 2006/112/EC), `VATEX-EU-143-1F` (VATEX-EU-143-1F - Exempt based on article 143, section 1 (f) of Council Directive 2006/112/EC), `VATEX-EU-143-1FA` (VATEX-EU-143-1FA - Exempt based on article 143, section 1 (fa) of Council Directive 2006/112/EC), `VATEX-EU-143-1G` (VATEX-EU-143-1G - Exempt based on article 143, section 1 (g) of Council Directive 2006/112/EC), `VATEX-EU-143-1H` (VATEX-EU-143-1H - Exempt based on article 143, section 1 (h) of Council Directive 2006/112/EC), `VATEX-EU-143-1I` (VATEX-EU-143-1I - Exempt based on article 143, section 1 (i) of Council Directive 2006/112/EC), `VATEX-EU-143-1J` (VATEX-EU-143-1J - Exempt based on article 143, section 1 (j) of Council Directive 2006/112/EC), `VATEX-EU-143-1K` (VATEX-EU-143-1K - Exempt based on article 143, section 1 (k) of Council Directive 2006/112/EC), `VATEX-EU-143-1L` (VATEX-EU-143-1L - Exempt based on article 143, section 1 (l) of Council Directive 2006/112/EC), `VATEX-EU-144` (VATEX-EU-144 - Exempt based on article 144 of Council Directive 2006/112/EC), `VATEX-EU-146-1E` (VATEX-EU-146-1E - Exempt based on article 146 section 1 (e) of Council Directive 2006/112/EC), `VATEX-EU-148` (VATEX-EU-148 - Exempt based on article 148 of Council Directive 2006/112/EC), `VATEX-EU-148-A` (VATEX-EU-148-A - Exempt based on article 148, section (a) of Council Directive 2006/112/EC), `VATEX-EU-148-B` (VATEX-EU-148-B - Exempt based on article 148, section (b) of Council Directive 2006/112/EC), `VATEX-EU-148-C` (VATEX-EU-148-C - Exempt based on article 148, section (c) of Council Directive 2006/112/EC), `VATEX-EU-148-D` (VATEX-EU-148-D - Exempt based on article 148, section (d) of Council Directive 2006/112/EC), `VATEX-EU-148-E` (VATEX-EU-148-E - Exempt based on article 148, section (e) of Council Directive 2006/112/EC), `VATEX-EU-148-F` (VATEX-EU-148-F - Exempt based on article 148, section (f) of Council Directive 2006/112/EC), `VATEX-EU-148-G` (VATEX-EU-148-G - Exempt based on article 148, section (g) of Council Directive 2006/112/EC), `VATEX-EU-151` (VATEX-EU-151 - Exempt based on article 151 of Council Directive 2006/112/EC), `VATEX-EU-151-1A` (VATEX-EU-151-1A - Exempt based on article 151, section 1 (a) of Council Directive 2006/112/EC), `VATEX-EU-151-1AA` (VATEX-EU-151-1AA - Exempt based on article 151, section 1 (aa) of Council Directive 2006/112/EC), `VATEX-EU-151-1B` (VATEX-EU-151-1B - Exempt based on article 151, section 1 (b) of Council Directive 2006/112/EC), `VATEX-EU-151-1C` (VATEX-EU-151-1C - Exempt based on article 151, section 1 (c) of Council Directive 2006/112/EC), `VATEX-EU-151-1D` (VATEX-EU-151-1D - Exempt based on article 151, section 1 (d) of Council Directive 2006/112/EC), `VATEX-EU-151-1E` (VATEX-EU-151-1E - Exempt based on article 151, section 1 (e) of Council Directive 2006/112/EC), `VATEX-EU-153` (VATEX-EU-153 - Exempt based on article 153 of Council Directive 2006/112/EC), `VATEX-EU-159` (VATEX-EU-159 - Exempt based on article 159 of Council Directive 2006/112/EC), `VATEX-EU-309` (VATEX-EU-309 - Exempt based on article 309 of Council Directive 2006/112/EC), `VATEX-EU-AE` (VATEX-EU-AE - Reverse charge), `VATEX-EU-D` (VATEX-EU-D - Intra-Community acquisition from second hand means of transport), `VATEX-EU-F` (VATEX-EU-F - Intra-Community acquisition of second hand goods), `VATEX-EU-G` (VATEX-EU-G - Export outside the EU), `VATEX-EU-I` (VATEX-EU-I - Intra-Community acquisition of works of art), `VATEX-EU-IC` (VATEX-EU-IC - Intra-Community supply), `VATEX-EU-O` (VATEX-EU-O - Not subject to VAT), `VATEX-EU-J` (VATEX-EU-J - Intra-Community acquisition of collectors items and antiques), `VATEX-FR-FRANCHISE` (VATEX-FR-FRANCHISE - France domestic VAT franchise in base), `VATEX-FR-CNWVAT` (VATEX-FR-CNWVAT - France domestic Credit Notes without VAT, due to supplier forfeit of VAT for discount), `VATEX-FR-CGI261-1` (VATEX-FR-CGI261-1 - Exempt based on 1 of article 261 of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261-2` (VATEX-FR-CGI261-2 - Exempt based on 2 of article 261 of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261-3` (VATEX-FR-CGI261-3 - Exempt based on 3 of article 261 of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261-4` (VATEX-FR-CGI261-4 - Exempt based on 4 of article 261 of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261-5` (VATEX-FR-CGI261-5 - Exempt based on 5 of article 261 of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261-7` (VATEX-FR-CGI261-7 - Exempt based on 7 of article 261 of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261-8` (VATEX-FR-CGI261-8 - Exempt based on 8 of article 261 of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261A` (VATEX-FR-CGI261A - Exempt based on article 261 A of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261B` (VATEX-FR-CGI261B - Exempt based on article 261 B of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261C-1` (VATEX-FR-CGI261C-1 - Exempt based on 1° of article 261 C of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261C-2` (VATEX-FR-CGI261C-2 - Exempt based on 2° of article 261 C of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261C-3` (VATEX-FR-CGI261C-3 - Exempt based on 3° of article 261 C of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261D-1` (VATEX-FR-CGI261D-1 - Exempt based on 1° of article 261 D of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261D-1BIS` (VATEX-FR-CGI261D-1BIS - Exempt based on 1°bis of article 261 D of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261D-2` (VATEX-FR-CGI261D-2 - Exempt based on 2° of article 261 D of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261D-3` (VATEX-FR-CGI261D-3 - Exempt based on 3° of article 261 D of the Code Général des Impôts (CGI ; General tax code) Exonération de TVA - Article 261 D-3° du Code Général des Impôts), `VATEX-FR-CGI261D-4` (VATEX-FR-CGI261D-4 - Exempt based on 4° of article 261 D of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261E-1` (VATEX-FR-CGI261E-1 - Exempt based on 1° of article 261 E of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI261E-2` (VATEX-FR-CGI261E-2 - Exempt based on 2° of article 261 E of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI277A` (VATEX-FR-CGI277A - Exempt based on article 277 A of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI275` (VATEX-FR-CGI275 - Exempt based on article 275 of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-298SEXDECIESA` (VATEX-FR-298SEXDECIESA - Exempt based on article 298 sexdecies A of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-CGI295` (VATEX-FR-CGI295 - Exempt based on article 295 of the Code Général des Impôts (CGI ; General tax code)), `VATEX-FR-AE` (VATEX-FR-AE - Exempt based on 2 of article 283 of the Code Général des Impôts (CGI ; General tax code))
- `tax_discount` **(boolean)** — Discount this Tax in Price
  > Mark it for (ICMS, PIS e etc.).
- `l10n_br_avatax_code` **(char)** — Avatax Code 🔒 readonly
  > Technical field containing the Avatax identifier for this tax.

## Relacionamentos

- `fiscal_position_ids` **(many2many)** — Fiscal Position → `account.fiscal.position`
- `original_tax_ids` **(many2many)** — Replaces → `account.tax`
  > List of taxes to replace when applying any of the stipulated fiscal positions.
- `replacing_tax_ids` **(many2many)** — Replaced by 🔒 readonly → `account.tax`
- `children_tax_ids` **(many2many)** — Children Taxes → `account.tax`
- `cash_basis_transition_account_id` **(many2one)** — Cash Basis Transition Account → `account.account`
  > Account used to transition the tax amount for cash basis taxes. It will contain the tax amount as long as the original invoice has not been reconciled ; at reconciliation, this amount cancelled on this account and put on the regular tax account.
- `invoice_repartition_line_ids` **(one2many)** — Distribution for Invoices → `account.tax.repartition.line`
  > Distribution when the tax is used on an invoice
- `refund_repartition_line_ids` **(one2many)** — Distribution for Refund Invoices → `account.tax.repartition.line`
  > Distribution when the tax is used on a refund
- `repartition_line_ids` **(one2many)** — Distribution → `account.tax.repartition.line`

## Campos Calculados (readonly)

- `display_alternative_taxes_field` **(boolean)** — Display Alternative Taxes Field 🔒 readonly
- `tax_label` **(char)** — Tax Label 🔒 readonly
- `price_include` **(boolean)** — Price Include 🔒 readonly
  > Determines whether the price you use on the product and invoices includes this tax.
- `company_price_include` **(selection)** — Default Sales Price Include 🔒 readonly
  > Default on whether the sales price used on the product and invoices with this Company includes its taxes.
  > Opções: `tax_included` (Tax Included), `tax_excluded` (Tax Excluded)
- `hide_tax_exigibility` **(boolean)** — Hide Use Cash Basis Option 🔒 readonly
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `is_used` **(boolean)** — Tax used 🔒 readonly
- `repartition_lines_str` **(char)** — Repartition Lines 🔒 readonly
- `has_negative_factor` **(boolean)** — Has Negative Factor 🔒 readonly
- `ubl_cii_requires_exemption_reason` **(boolean)** — Ubl Cii Requires Exemption Reason 🔒 readonly
