# Accounting Report — `account.report`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `active` **(boolean)** — Active
- `use_sections` **(boolean)** — Composite Report
  > Create a structured report with multiple sections for convenient navigation and simultaneous printing.
- `chart_template` **(selection)** — Chart of Accounts
  > Opções: `br` (🇧🇷 Brazil), `generic_coa` (Generic Chart of Accounts), `ae` (🇦🇪 United Arab Emirates), `ar_ri` (🇦🇷 Argentina - Argentine Generic Chart of Accounts for Registered Accountants), `ar_base` (🇦🇷 Argentina - Generic Chart of Accounts Argentina Single Taxpayer / Basis), `ar_ex` (🇦🇷 Argentina - Argentine Generic Chart of Accounts for Exempt Individuals), `at` (🇦🇹 Austria), `au` (🇦🇺 Australia), `bd` (🇧🇩 Bangladesh), `be_comp` (🇧🇪 Belgium - Companies), `be_asso` (🇧🇪 Belgium - Associations and Foundations), `bf` (🇧🇫 Burkina Faso - SYSCOHADA for Companies), `bf_syscebnl` (🇧🇫 Burkina Faso - SYSCEBNL for Associations), `bg` (🇧🇬 Bulgaria), `bh` (🇧🇭 Bahrain), `bj` (🇧🇯 Benin - SYSCOHADA for Companies), `bj_syscebnl` (🇧🇯 Benin - SYSCEBNL for Associations), `bo` (🇧🇴 Bolivia), `ca_2023` (🇨🇦 Canada), `cd` (🇨🇩 Congo (DRC) - SYSCOHADA for Companies), `cd_syscebnl` (🇨🇩 Congo (DRC) - SYSCEBNL for Associations), `cf` (🇨🇫 Central African Republic - SYSCOHADA for Companies), `cf_syscebnl` (🇨🇫 Central African Republic - SYSCEBNL for Associations), `cg` (🇨🇬 Congo (Republic) - SYSCOHADA for Companies), `cg_syscebnl` (🇨🇬 Congo (Republic) - SYSCEBNL for Associations), `ch` (🇨🇭 Switzerland), `ci` (🇨🇮 Côte d'Ivoire - SYSCOHADA for Companies), `ci_syscebnl` (🇨🇮 Côte d'Ivoire - SYSCEBNL for Associations), `cl` (🇨🇱 Chile), `cm` (🇨🇲 Cameroon - SYSCOHADA for Companies), `cm_syscebnl` (🇨🇲 Cameroon - SYSCEBNL for Associations), `cn` (🇨🇳 China - Accounting Standards for Small Business Enterprises), `cn_large_bis` (🇨🇳 China - Accounting Standards for Business Enterprises), `co` (🇨🇴 Colombia), `cr` (🇨🇷 Costa Rica), `cy` (🇨🇾 Cyprus), `cz` (🇨🇿 Czech Republic), `de_skr03` (🇩🇪 Germany - German Chart of Accounts SKR03), `de_skr04` (🇩🇪 Germany - German chart of accounts SKR04), `dk` (🇩🇰 Denmark), `do` (🇩🇴 Dominican Republic), `dz` (🇩🇿 Algeria), `ec` (🇪🇨 Ecuador), `ee` (🇪🇪 Estonia), `eg` (🇪🇬 Egypt), `es_pymes` (🇪🇸 Spain - SMEs (2008)), `es_assec` (🇪🇸 Spain - Non-profit entities (2008)), `es_canary_assoc` (🇪🇸 Spain - Canary Islands - PGCE non-profit entities (2008)), `es_canary_full` (🇪🇸 Spain - Canary Islands - Complete (2008)), `es_canary_pymes` (🇪🇸 Spain - Canary Islands - SMEs (2008)), `es_coop_full` (🇪🇸 Spain - Cooperatives - Complete (2008)), `es_coop_pymes` (🇪🇸 Spain - Cooperatives - SMEs (2008)), `es_full` (🇪🇸 Spain - Complete (2008)), `et` (🇪🇹 Ethiopia), `fi` (🇫🇮 Finland), `fr` (🇫🇷 France), `mc` (🇲🇨 Monaco), `ga` (🇬🇦 Gabon - SYSCOHADA for Companies), `ga_syscebnl` (🇬🇦 Gabon - SYSCEBNL for Associations), `gn` (🇬🇳 Guinea - SYSCOHADA for Companies), `gn_syscebnl` (🇬🇳 Guinea - SYSCEBNL for Associations), `gq` (🇬🇶 Equatorial Guinea - SYSCOHADA for Companies), `gq_syscebnl` (🇬🇶 Equatorial Guinea - SYSCEBNL for Associations), `gr` (🇬🇷 Greece), `gt` (🇬🇹 Guatemala), `gw` (🇬🇼 Guinea-Bissau - SYSCOHADA for Companies), `gw_syscebnl` (🇬🇼 Guinea-Bissau - SYSCEBNL for Associations), `hk` (🇭🇰 Hong Kong), `hn` (🇭🇳 Honduras), `hr` (🇭🇷 Croatia), `hr_kuna` (🇭🇷 Croatia - RRIF-ov računski plan za poduzetnike), `hu` (🇭🇺 Hungary), `id` (🇮🇩 Indonesia), `ie` (🇮🇪 Ireland), `il` (🇮🇱 Israel), `in` (🇮🇳 India), `iq` (🇮🇶 Iraq), `it` (🇮🇹 Italy), `jo_standard` (🇯🇴 Jordan), `jp` (🇯🇵 Japan), `ke` (🇰🇪 Kenya), `kh` (🇰🇭 Cambodia), `km` (🇰🇲 Comoros - SYSCOHADA for Companies), `km_syscebnl` (🇰🇲 Comoros - SYSCEBNL for Associations), `kr` (🇰🇷 South Korea), `kw` (🇰🇼 Kuwait), `kz` (🇰🇿 Kazakhstan), `lb` (🇱🇧 Lebanon), `lk` (🇱🇰 Sri Lanka), `lt` (🇱🇹 Lithuania), `lu` (🇱🇺 Luxembourg), `lv` (🇱🇻 Latvia), `ma` (🇲🇦 Morocco), `ml` (🇲🇱 Mali - SYSCOHADA for Companies), `ml_syscebnl` (🇲🇱 Mali - SYSCEBNL for Associations), `mn` (🇲🇳 Mongolia), `mr` (🇲🇷 Mauritania), `mt` (🇲🇹 Malta), `mu` (🇲🇺 Mauritius), `mx` (🇲🇽 Mexico), `my` (🇲🇾 Malaysia), `mz` (🇲🇿 Mozambique), `ne` (🇳🇪 Niger - SYSCOHADA for Companies), `ne_syscebnl` (🇳🇪 Niger - SYSCEBNL for Associations), `ng` (🇳🇬 Nigeria), `nl` (🇳🇱 Netherlands), `no` (🇳🇴 Norway), `nz` (🇳🇿 New Zealand), `om` (🇴🇲 Oman), `pa` (🇵🇦 Panama), `pe` (🇵🇪 Peru), `ph` (🇵🇭 Philippines), `pk` (🇵🇰 Pakistan), `pl` (🇵🇱 Poland), `pt` (🇵🇹 Portugal), `qa` (🇶🇦 Qatar), `ro` (🇷🇴 Romania), `rs` (🇷🇸 Serbia), `rw` (🇷🇼 Rwanda), `sa` (🇸🇦 Saudi Arabia), `se` (🇸🇪 Sweden), `se_K2` (🇸🇪 Sweden - Swedish BAS Chart of Account complete K2), `se_K3` (🇸🇪 Sweden - Swedish BAS Chart of Account complete K3), `sg` (🇸🇬 Singapore), `si` (🇸🇮 Slovenia), `sk` (🇸🇰 Slovakia), `sn` (🇸🇳 Senegal - SYSCOHADA for Companies), `sn_syscebnl` (🇸🇳 Senegal - SYSCEBNL for Associations), `syscebnl` (SYSCEBNL), `syscohada` (SYSCOHADA - Revised), `td` (🇹🇩 Chad - SYSCOHADA for Companies), `td_syscebnl` (🇹🇩 Chad - SYSCEBNL for Associations), `tg` (🇹🇬 Togo - SYSCOHADA for Companies), `tg_syscebnl` (🇹🇬 Togo - SYSCEBNL for Associations), `th` (🇹🇭 Thailand), `tn` (🇹🇳 Tunisia), `tr` (🇹🇷 Türkiye), `tw` (🇹🇼 Taiwan), `tz` (🇹🇿 Tanzania), `ua_psbo` (🇺🇦 Ukraine - IFRS Chart of Accounts), `ug` (🇺🇬 Uganda - Uganda Generic Chart of Accounts), `uk` (🇬🇧 United Kingdom), `xi` (🇽🇮 Northern Ireland), `us` (🇺🇸 United States), `uy` (🇺🇾 Uruguay - Uruguayan Generic Chart of Accounts), `uz` (🇺🇿 Uzbekistan), `ve` (🇻🇪 Venezuela), `vn` (🇻🇳 Vietnam), `za` (🇿🇦 South Africa), `zm` (🇿🇲 Zambia)
- `only_tax_exigible` **(boolean)** — Only Tax Exigible Lines
- `availability_condition` **(selection)** — Availability
  > Opções: `country` (Country Matches), `coa` (Chart of Accounts Matches), `always` (Always)
- `load_more_limit` **(integer)** — Load More Limit
- `search_bar` **(boolean)** — Search Bar
- `prefix_groups_threshold` **(integer)** — Prefix Groups Threshold
- `integer_rounding` **(selection)** — Integer Rounding
  > Opções: `HALF-UP` (Nearest), `UP` (Up), `DOWN` (Down)
- `allow_foreign_vat` **(boolean)** — Allow Foreign VAT
- `default_opening_date_filter` **(selection)** — Default Opening
  > Opções: `this_year` (This Year), `this_quarter` (This Quarter), `this_month` (This Month), `today` (Today), `previous_month` (Last Month), `previous_quarter` (Last Quarter), `previous_year` (Last Year), `this_return_period` (This Return Period), `previous_return_period` (Last Return Period)
- `currency_translation` **(selection)** — Currency Translation
  > Opções: `current` (Use the most recent rate at the date of the report), `cta` (Use CTA)
- `filter_multi_company` **(selection)** — Multi-Company
  > Opções: `selector` (Use Company Selector), `tax_units` (Use Tax Units)
- `filter_date_range` **(boolean)** — Date Range
- `filter_show_draft` **(boolean)** — Draft Entries
- `filter_unreconciled` **(boolean)** — Unreconciled Entries
- `filter_unfold_all` **(boolean)** — Unfold All
- `filter_hide_0_lines` **(selection)** — Hide lines at 0
  > Opções: `by_default` (Enabled by Default), `optional` (Optional), `never` (Never)
- `filter_period_comparison` **(boolean)** — Period Comparison
- `filter_growth_comparison` **(boolean)** — Growth Comparison
- `filter_journals` **(boolean)** — Journals
- `filter_analytic` **(boolean)** — Analytic Filter
- `filter_hierarchy` **(selection)** — Account Groups
  > Opções: `by_default` (Enabled by Default), `optional` (Optional), `never` (Never)
- `filter_account_type` **(selection)** — Account Types
  > Opções: `both` (Payable and receivable), `payable` (Payable), `receivable` (Receivable), `disabled` (Disabled)
- `filter_partner` **(boolean)** — Partners
- `filter_aml_ir_filters` **(boolean)** — Favorite Filters
  > If activated, user-defined filters on journal items can be selected on this report
- `filter_budgets` **(boolean)** — Budgets
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `send_and_print_values` **(json)** — Send And Print Values
- `allow_account_audit_status_on_lines` **(boolean)** — Allow Account Audit Status On Lines
- `filter_analytic_groupby` **(boolean)** — Analytic Group By

## Relacionamentos

- `line_ids` **(one2many)** — Lines → `account.report.line`
- `column_ids` **(one2many)** — Columns → `account.report.column`
- `root_report_id` **(many2one)** — Root Report → `account.report`
  > The report this report is a variant of.
- `variant_report_ids` **(one2many)** — Variants → `account.report`
- `section_report_ids` **(many2many)** — Sections → `account.report`
- `section_main_report_ids` **(many2many)** — Section Of → `account.report`
- `country_id` **(many2one)** — Country → `res.country`
- `horizontal_group_ids` **(many2many)** — Horizontal Groups → `account.report.horizontal.group`
- `return_type_ids` **(one2many)** — Return Types → `account.return.type`
- `custom_handler_model_id` **(many2one)** — Custom Handler Model → `ir.model`

## Campos Calculados (readonly)

- `custom_handler_model_name` **(char)** — Custom Handler Model Name 🔒 readonly
- `is_account_coverage_report_available` **(boolean)** — Is Account Coverage Report Available 🔒 readonly
