# Companies — `res.company`

**Ordenação padrão:** `sequence, name`

---

## Campos Obrigatórios

- `name` **(char)** — Company Name ⚠️ obrigatório
- `partner_id` **(many2one)** — Partner ⚠️ obrigatório → `res.partner`
- `currency_id` **(many2one)** — Currency ⚠️ obrigatório → `res.currency`
- `layout_background` **(selection)** — Layout Background ⚠️ obrigatório
  > Opções: `Blank` (Blank), `Demo logo` (Demo logo), `Custom` (Custom)
- `fiscalyear_last_day` **(integer)** — Fiscalyear Last Day ⚠️ obrigatório
- `fiscalyear_last_month` **(selection)** — Fiscalyear Last Month ⚠️ obrigatório
  > Opções: `1` (January), `2` (February), `3` (March), `4` (April), `5` (May), `6` (June), `7` (July), `8` (August), `9` (September), `10` (October), `11` (November), `12` (December)
- `account_price_include` **(selection)** — Default Sales Price Include ⚠️ obrigatório
  > Default on whether the sales price used on the product and invoices with this Company includes its taxes.
  > Opções: `tax_included` (Tax Included), `tax_excluded` (Tax Excluded)
- `horizon_days` **(float)** — Replenishment Horizon ⚠️ obrigatório
  > Configure your horizon to trigger reordering rules earlier to get                                 a head start on replenishment and avoid delays, or trigger it just-in-time                                 ('0 days') to avoid overstocking.
- `generate_deferred_expense_entries_method` **(selection)** — Generate Deferred Expense Entries ⚠️ obrigatório
  > Opções: `on_validation` (On bill validation), `manual` (Manually & Grouped)
- `deferred_expense_amount_computation_method` **(selection)** — Deferred Expense Based on ⚠️ obrigatório
  > Opções: `day` (Days), `month` (Months), `full_months` (Full Months)
- `generate_deferred_revenue_entries_method` **(selection)** — Generate Deferred Revenue Entries ⚠️ obrigatório
  > Opções: `on_validation` (On bill validation), `manual` (Manually & Grouped)
- `deferred_revenue_amount_computation_method` **(selection)** — Deferred Revenue Based on ⚠️ obrigatório
  > Opções: `day` (Days), `month` (Months), `full_months` (Full Months)
- `currency_interval_unit` **(selection)** — Interval Unit ⚠️ obrigatório
  > Opções: `manually` (Manually), `daily` (Daily), `weekly` (Weekly), `monthly` (Monthly)
- `inventory_period` **(selection)** — Inventory Period ⚠️ obrigatório
  > Opções: `manual` (Manual), `daily` (Daily), `monthly` (Monthly)
- `cost_method` **(selection)** — Cost Method ⚠️ obrigatório
  > Opções: `standard` (Standard Price), `fifo` (First In First Out (FIFO)), `average` (Average Cost (AVCO))
- `account_return_periodicity` **(selection)** — Delay units ⚠️ obrigatório
  > Periodicity
  > Opções: `monthly` (Monthly), `2_months` (Every 2 months), `trimester` (Quarterly), `4_months` (Every 4 months), `semester` (Semi-annually), `year` (Annually), `fiscalyear` (Fiscal Year)
- `account_return_reminder_day` **(integer)** — Start from ⚠️ obrigatório
- `planning_generation_interval` **(integer)** — Rate Of Shift Generation ⚠️ obrigatório
- `planning_employee_unavailabilities` **(selection)** — Employee Unavailabilities ⚠️ obrigatório
  > Opções: `switch` (Switch shifts with other employees), `unassign` (Unassign themselves from shifts)
- `manufacturing_period` **(selection)** — Manufacturing Period ⚠️ obrigatório
  > Default value for the time ranges in Master Production Schedule report.
  > Opções: `year` (Yearly), `month` (Monthly), `week` (Weekly), `day` (Daily)
- `security_lead` **(float)** — Sales Safety Days ⚠️ obrigatório
  > Margin of error for dates promised to customers. Products will be scheduled for procurement and delivery that many days earlier than the actual promised date, to cope with unexpected delays in the supply chain.
- `timesheet_mail_employee_interval` **(selection)** — Employee Frequency ⚠️ obrigatório
  > Opções: `weeks` (after the end of the week), `months` (after the end of the month)
- `timesheet_mail_interval` **(selection)** — Approver Reminder Frequency ⚠️ obrigatório
  > Opções: `weeks` (after the end of the week), `months` (after the end of the month)
- `l10n_br_avalara_environment` **(selection)** — Avalara Brazil Environment ⚠️ obrigatório
  > Opções: `sandbox` (Sandbox), `production` (Production)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
  > Used to order Companies in the company switcher
- `parent_path` **(char)** — Parent Path
- `report_header` **(html)** — Company Tagline
  > Company tagline, which is included in a printed document's header or footer (depending on the selected layout).
- `report_footer` **(html)** — Report Footer
  > Footer text displayed at the bottom of all reports.
- `company_details` **(html)** — Company Details
  > Header text displayed at the top of all reports.
- `logo` **(binary)** — Company Logo
- `logo_web` **(binary)** — Logo Web 🔒 readonly
- `uses_default_logo` **(boolean)** — Uses Default Logo 🔒 readonly
- `street` **(char)** — Street
- `street2` **(char)** — Street2
- `zip` **(char)** — Zip
- `city` **(char)** — City
- `email` **(char)** — Email
- `phone` **(char)** — Phone
- `website` **(char)** — Website Link
- `vat` **(char)** — Tax ID
  > Identification Number for selected type
- `company_registry` **(char)** — Company ID
  > The registry number of the company. Use it if it is different from the Tax ID. It must be unique across all partners of a same country
- `font` **(selection)** — Font
  > Opções: `Lato` (Lato), `Roboto` (Roboto), `Open_Sans` (Open Sans), `Montserrat` (Montserrat), `Oswald` (Oswald), `Raleway` (Raleway), `Tajawal` (Tajawal), `Fira_Mono` (Fira Mono)
- `primary_color` **(char)** — Primary Color
- `secondary_color` **(char)** — Secondary Color
- `color` **(integer)** — Color
- `layout_background_image` **(binary)** — Background Image
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `social_twitter` **(char)** — X Account
- `social_facebook` **(char)** — Facebook Account
- `social_github` **(char)** — GitHub Account
- `social_linkedin` **(char)** — LinkedIn Account
- `social_youtube` **(char)** — Youtube Account
- `social_instagram` **(char)** — Instagram Account
- `social_tiktok` **(char)** — TikTok Account
- `social_discord` **(char)** — Discord Account
- `email_primary_color` **(char)** — Email Button Text
- `email_secondary_color` **(char)** — Email Button Color
- `iap_enrich_auto_done` **(boolean)** — Enrich Done
- `snailmail_color` **(boolean)** — Snailmail Color
- `snailmail_cover` **(boolean)** — Add a Cover Page
- `snailmail_duplex` **(boolean)** — Both sides
- `sign_terms` **(html)** — Sign Default Terms and Conditions
- `sign_terms_type` **(selection)** — Sign Terms & Conditions format
  > Terms in Email - The text will be displayed at the bottom of every signature request email.          Terms as Web Page - A link will be pasted at the bottom of every signature request email, leading to your content.         
  > Opções: `plain` (Terms in Email), `html` (Terms as Web Page)
- `sign_terms_html` **(html)** — Sign Default Terms and Conditions as a Web page
- `fiscalyear_lock_date` **(date)** — Global Lock Date
  > Any entry up to and including that date will be postponed to a later time, in accordance with its journal's sequence.
- `tax_lock_date` **(date)** — Tax Return Lock Date
  > Any entry with taxes up to and including that date will be postponed to a later time, in accordance with its journal's sequence. The tax lock date is automatically set when the tax closing entry is posted.
- `sale_lock_date` **(date)** — Sales Lock Date
  > Any sales entry prior to and including this date will be postponed to a later date, in accordance with its journal's sequence.
- `purchase_lock_date` **(date)** — Purchase Lock date
  > Any purchase entry prior to and including this date will be postponed to a later date, in accordance with its journal's sequence.
- `hard_lock_date` **(date)** — Hard Lock Date
  > Any entry up to and including that date will be postponed to a later time, in accordance with its journal sequence. This lock date is irreversible and does not allow any exception.
- `expects_chart_of_accounts` **(boolean)** — Expects a Chart of Accounts
- `chart_template` **(selection)** — Chart Template
  > Opções: `generic_coa` (Generic Chart of Accounts), `ae` (🇦🇪 United Arab Emirates), `ar_ri` (🇦🇷 Argentina - Argentine Generic Chart of Accounts for Registered Accountants), `ar_base` (🇦🇷 Argentina - Generic Chart of Accounts Argentina Single Taxpayer / Basis), `ar_ex` (🇦🇷 Argentina - Argentine Generic Chart of Accounts for Exempt Individuals), `at` (🇦🇹 Austria), `au` (🇦🇺 Australia), `bd` (🇧🇩 Bangladesh), `be_comp` (🇧🇪 Belgium - Companies), `be_asso` (🇧🇪 Belgium - Associations and Foundations), `bf` (🇧🇫 Burkina Faso - SYSCOHADA for Companies), `bf_syscebnl` (🇧🇫 Burkina Faso - SYSCEBNL for Associations), `bg` (🇧🇬 Bulgaria), `bh` (🇧🇭 Bahrain), `bj` (🇧🇯 Benin - SYSCOHADA for Companies), `bj_syscebnl` (🇧🇯 Benin - SYSCEBNL for Associations), `bo` (🇧🇴 Bolivia), `br` (🇧🇷 Brazil), `ca_2023` (🇨🇦 Canada), `cd` (🇨🇩 Congo (DRC) - SYSCOHADA for Companies), `cd_syscebnl` (🇨🇩 Congo (DRC) - SYSCEBNL for Associations), `cf` (🇨🇫 Central African Republic - SYSCOHADA for Companies), `cf_syscebnl` (🇨🇫 Central African Republic - SYSCEBNL for Associations), `cg` (🇨🇬 Congo (Republic) - SYSCOHADA for Companies), `cg_syscebnl` (🇨🇬 Congo (Republic) - SYSCEBNL for Associations), `ch` (🇨🇭 Switzerland), `ci` (🇨🇮 Côte d'Ivoire - SYSCOHADA for Companies), `ci_syscebnl` (🇨🇮 Côte d'Ivoire - SYSCEBNL for Associations), `cl` (🇨🇱 Chile), `cm` (🇨🇲 Cameroon - SYSCOHADA for Companies), `cm_syscebnl` (🇨🇲 Cameroon - SYSCEBNL for Associations), `cn` (🇨🇳 China - Accounting Standards for Small Business Enterprises), `cn_large_bis` (🇨🇳 China - Accounting Standards for Business Enterprises), `co` (🇨🇴 Colombia), `cr` (🇨🇷 Costa Rica), `cy` (🇨🇾 Cyprus), `cz` (🇨🇿 Czech Republic), `de_skr03` (🇩🇪 Germany - German Chart of Accounts SKR03), `de_skr04` (🇩🇪 Germany - German chart of accounts SKR04), `dk` (🇩🇰 Denmark), `do` (🇩🇴 Dominican Republic), `dz` (🇩🇿 Algeria), `ec` (🇪🇨 Ecuador), `ee` (🇪🇪 Estonia), `eg` (🇪🇬 Egypt), `es_pymes` (🇪🇸 Spain - SMEs (2008)), `es_assec` (🇪🇸 Spain - Non-profit entities (2008)), `es_canary_assoc` (🇪🇸 Spain - Canary Islands - PGCE non-profit entities (2008)), `es_canary_full` (🇪🇸 Spain - Canary Islands - Complete (2008)), `es_canary_pymes` (🇪🇸 Spain - Canary Islands - SMEs (2008)), `es_coop_full` (🇪🇸 Spain - Cooperatives - Complete (2008)), `es_coop_pymes` (🇪🇸 Spain - Cooperatives - SMEs (2008)), `es_full` (🇪🇸 Spain - Complete (2008)), `et` (🇪🇹 Ethiopia), `fi` (🇫🇮 Finland), `fr` (🇫🇷 France), `mc` (🇲🇨 Monaco), `ga` (🇬🇦 Gabon - SYSCOHADA for Companies), `ga_syscebnl` (🇬🇦 Gabon - SYSCEBNL for Associations), `gn` (🇬🇳 Guinea - SYSCOHADA for Companies), `gn_syscebnl` (🇬🇳 Guinea - SYSCEBNL for Associations), `gq` (🇬🇶 Equatorial Guinea - SYSCOHADA for Companies), `gq_syscebnl` (🇬🇶 Equatorial Guinea - SYSCEBNL for Associations), `gr` (🇬🇷 Greece), `gt` (🇬🇹 Guatemala), `gw` (🇬🇼 Guinea-Bissau - SYSCOHADA for Companies), `gw_syscebnl` (🇬🇼 Guinea-Bissau - SYSCEBNL for Associations), `hk` (🇭🇰 Hong Kong), `hn` (🇭🇳 Honduras), `hr` (🇭🇷 Croatia), `hr_kuna` (🇭🇷 Croatia - RRIF-ov računski plan za poduzetnike), `hu` (🇭🇺 Hungary), `id` (🇮🇩 Indonesia), `ie` (🇮🇪 Ireland), `il` (🇮🇱 Israel), `in` (🇮🇳 India), `iq` (🇮🇶 Iraq), `it` (🇮🇹 Italy), `jo_standard` (🇯🇴 Jordan), `jp` (🇯🇵 Japan), `ke` (🇰🇪 Kenya), `kh` (🇰🇭 Cambodia), `km` (🇰🇲 Comoros - SYSCOHADA for Companies), `km_syscebnl` (🇰🇲 Comoros - SYSCEBNL for Associations), `kr` (🇰🇷 South Korea), `kw` (🇰🇼 Kuwait), `kz` (🇰🇿 Kazakhstan), `lb` (🇱🇧 Lebanon), `lk` (🇱🇰 Sri Lanka), `lt` (🇱🇹 Lithuania), `lu` (🇱🇺 Luxembourg), `lv` (🇱🇻 Latvia), `ma` (🇲🇦 Morocco), `ml` (🇲🇱 Mali - SYSCOHADA for Companies), `ml_syscebnl` (🇲🇱 Mali - SYSCEBNL for Associations), `mn` (🇲🇳 Mongolia), `mr` (🇲🇷 Mauritania), `mt` (🇲🇹 Malta), `mu` (🇲🇺 Mauritius), `mx` (🇲🇽 Mexico), `my` (🇲🇾 Malaysia), `mz` (🇲🇿 Mozambique), `ne` (🇳🇪 Niger - SYSCOHADA for Companies), `ne_syscebnl` (🇳🇪 Niger - SYSCEBNL for Associations), `ng` (🇳🇬 Nigeria), `nl` (🇳🇱 Netherlands), `no` (🇳🇴 Norway), `nz` (🇳🇿 New Zealand), `om` (🇴🇲 Oman), `pa` (🇵🇦 Panama), `pe` (🇵🇪 Peru), `ph` (🇵🇭 Philippines), `pk` (🇵🇰 Pakistan), `pl` (🇵🇱 Poland), `pt` (🇵🇹 Portugal), `qa` (🇶🇦 Qatar), `ro` (🇷🇴 Romania), `rs` (🇷🇸 Serbia), `rw` (🇷🇼 Rwanda), `sa` (🇸🇦 Saudi Arabia), `se` (🇸🇪 Sweden), `se_K2` (🇸🇪 Sweden - Swedish BAS Chart of Account complete K2), `se_K3` (🇸🇪 Sweden - Swedish BAS Chart of Account complete K3), `sg` (🇸🇬 Singapore), `si` (🇸🇮 Slovenia), `sk` (🇸🇰 Slovakia), `sn` (🇸🇳 Senegal - SYSCOHADA for Companies), `sn_syscebnl` (🇸🇳 Senegal - SYSCEBNL for Associations), `syscebnl` (SYSCEBNL), `syscohada` (SYSCOHADA - Revised), `td` (🇹🇩 Chad - SYSCOHADA for Companies), `td_syscebnl` (🇹🇩 Chad - SYSCEBNL for Associations), `tg` (🇹🇬 Togo - SYSCOHADA for Companies), `tg_syscebnl` (🇹🇬 Togo - SYSCEBNL for Associations), `th` (🇹🇭 Thailand), `tn` (🇹🇳 Tunisia), `tr` (🇹🇷 Türkiye), `tw` (🇹🇼 Taiwan), `tz` (🇹🇿 Tanzania), `ua_psbo` (🇺🇦 Ukraine - IFRS Chart of Accounts), `ug` (🇺🇬 Uganda - Uganda Generic Chart of Accounts), `uk` (🇬🇧 United Kingdom), `xi` (🇽🇮 Northern Ireland), `us` (🇺🇸 United States), `uy` (🇺🇾 Uruguay - Uruguayan Generic Chart of Accounts), `uz` (🇺🇿 Uzbekistan), `ve` (🇻🇪 Venezuela), `vn` (🇻🇳 Vietnam), `za` (🇿🇦 South Africa), `zm` (🇿🇲 Zambia)
- `bank_account_code_prefix` **(char)** — Prefix of the bank accounts
- `cash_account_code_prefix` **(char)** — Prefix of the cash accounts
- `transfer_account_code_prefix` **(char)** — Prefix of the transfer accounts
- `tax_calculation_rounding_method` **(selection)** — Tax Calculation Rounding Method
  > Opções: `round_globally` (Round per Tax), `round_per_line` (Round per Line)
- `anglo_saxon_accounting` **(boolean)** — Use anglo-saxon accounting
- `qr_code` **(boolean)** — Display QR-code on invoices
- `link_qr_code` **(boolean)** — Display Link QR-code
- `display_invoice_amount_total_words` **(boolean)** — Total amount of invoice in letters
- `display_invoice_tax_company_currency` **(boolean)** — Taxes in company currency
- `account_use_credit_limit` **(boolean)** — Sales Credit Limit
  > Enable the use of credit limit on partners.
- `account_opening_date` **(date)** — Opening Entry
  > That is the date of the opening entry.
- `invoice_terms` **(html)** — Default Terms and Conditions
- `terms_type` **(selection)** — Terms & Conditions format
  > Opções: `plain` (Add a Note), `html` (Add a link to a Web Page)
- `invoice_terms_html` **(html)** — Default Terms and Conditions as a Web page
- `tax_exigibility` **(boolean)** — Use Cash Basis
- `account_storno` **(boolean)** — Storno accounting
- `quick_edit_mode` **(selection)** — Quick encoding
  > Opções: `out_invoices` (Customer Invoices), `in_invoices` (Vendor Bills), `out_and_in_invoices` (Customer Invoices and Vendor Bills)
- `restrictive_audit_trail` **(boolean)** — Restrictive Audit Trail
  > Enable this option to prevent deletion of journal item related logs
- `autopost_bills` **(boolean)** — Auto-validate bills
- `hr_presence_control_email_amount` **(integer)** — # emails to send
- `hr_presence_control_ip_list` **(char)** — Valid IP addresses
- `employee_properties_definition` **(properties_definition)** — Employee Properties
- `hr_presence_control_login` **(boolean)** — Based on user status in system
- `hr_presence_control_email` **(boolean)** — Based on number of emails sent
- `hr_presence_control_ip` **(boolean)** — Based on IP Address
- `hr_presence_control_attendance` **(boolean)** — Based on attendances
- `contract_expiration_notice_period` **(integer)** — Contract Expiry Notice Period
- `work_permit_expiration_notice_period` **(integer)** — Work Permit Expiry Notice Period
- `stock_move_email_validation` **(boolean)** — Email Confirmation picking
- `annual_inventory_month` **(selection)** — Annual Inventory Month
  > Annual inventory month for products not in a location with a cyclic inventory date. Set to no month if no automatic annual inventory.
  > Opções: `1` (January), `2` (February), `3` (March), `4` (April), `5` (May), `6` (June), `7` (July), `8` (August), `9` (September), `10` (October), `11` (November), `12` (December)
- `annual_inventory_day` **(integer)** — Day of the month
  > Day of the month when the annual inventory should occur. If zero or negative, then the first day of the month will be selected instead.         If greater than the last day of a month, then the last day of the month will be selected instead.
- `stock_text_confirmation` **(boolean)** — Stock Text Confirmation
- `stock_confirmation_type` **(selection)** — Stock Confirmation Type
  > Opções: `sms` (SMS), `whatsapp` (Whatsapp)
- `invoicing_switch_threshold` **(date)** — Invoicing Switch Threshold
  > Every payment and invoice before this date will receive the 'From Invoicing' status, hiding all the accounting entries related to it. Use this option after installing Accounting if you were using only Invoicing before, before importing all your actual accounting data in to Odoo.
- `predict_bill_product` **(boolean)** — Predict Bill Product
- `sign_invoice` **(boolean)** — Display signing field on invoices
- `vat_check_vies` **(boolean)** — Verify VAT Numbers
- `currency_next_execution_date` **(date)** — Next Execution Date
- `currency_provider` **(selection)** — Service Provider
  > Opções: `ecb` (European Central Bank), `xe_com` (xe.com), `cbuae` ([AE] Central Bank of the UAE), `bnb` ([BG] Bulgaria National Bank), `bbr` ([BR] Central Bank of Brazil), `boc` ([CA] Bank of Canada), `fta` ([CH] Federal Tax Administration of Switzerland), `mindicador` ([CL] Central Bank of Chile via mindicador.cl), `banrepco` ([CO] Bank of the Republic), `cu` ([CU] Central Bank of Cuba), `cnb` ([CZ] Czech National Bank), `cbegy` ([EG] Central Bank of Egypt), `nbg` ([GE] National Bank of Georgia), `banguat` ([GT] Bank of Guatemala), `mnb` ([HU] Magyar Nemzeti Bank), `bi` ([ID] Bank Indonesia), `boi` ([IT] Bank of Italy), `nbkz` ([KZ] National Bank of Kazakhstan), `banxico` ([MX] Bank of Mexico), `bnm` ([MY] Bank Negara Malaysia), `bcrp` ([PE] SUNAT (replaces Bank of Peru)), `nbp` ([PL] National Bank of Poland), `bnr` ([RO] National Bank of Romania), `srb` ([SE] Sveriges Riksbank), `bsi` ([SI] Bank of Slovenia), `bot` ([TH] Bank of Thailand), `tcmb` ([TR] Central Bank of the Republic of Türkiye), `hmrc` ([UK] HM Revenue & Customs), `bcu` ([UY] Uruguayan Central Bank), `cbu` ([UZ] Central Bank of Uzbekistan)
- `documents_hr_settings` **(boolean)** — Documents Hr Settings
- `employee_subfolders` **(char)** — Employees Subfolder
  > Comma separated list of folder names that need to be created under each employee folder.
- `documents_product_settings` **(boolean)** — Documents Product Settings
- `overtime_company_threshold` **(integer)** — Tolerance Time In Favor Of Company
- `overtime_employee_threshold` **(integer)** — Tolerance Time In Favor Of Employee
- `hr_attendance_display_overtime` **(boolean)** — Display Extra Hours
- `attendance_kiosk_mode` **(selection)** — Attendance Mode
  > Opções: `barcode` (Barcode / RFID), `barcode_manual` (Barcode / RFID and Manual Selection), `manual` (Manual Selection)
- `attendance_barcode_source` **(selection)** — Barcode Source
  > Opções: `scanner` (Scanner), `front` (Front Camera), `back` (Back Camera)
- `attendance_kiosk_delay` **(integer)** — Attendance Kiosk Delay
- `attendance_kiosk_use_pin` **(boolean)** — Employee PIN Identification
- `attendance_from_systray` **(boolean)** — Attendance From Systray
- `attendance_overtime_validation` **(selection)** — Extra Hours Validation
  > Opções: `no_validation` (Automatically Approved), `by_manager` (Approved by Manager)
- `auto_check_out` **(boolean)** — Automatic Check Out
- `auto_check_out_tolerance` **(float)** — Auto Check Out Tolerance
- `absence_management` **(boolean)** — Absence Management
- `attendance_device_tracking` **(boolean)** — Device & Location Tracking
- `job_properties_definition` **(properties_definition)** — Job Properties
- `po_lock` **(selection)** — Purchase Order Modification
  > Purchase Order Modification used when you want to purchase order editable after confirm
  > Opções: `edit` (Allow to edit purchase orders), `lock` (Confirmed purchase orders are not editable)
- `po_double_validation` **(selection)** — Levels of Approvals
  > Provide a double validation mechanism for purchases
  > Opções: `one_step` (Confirm purchase orders in one step), `two_step` (Get 2 levels of approvals to confirm a purchase order)
- `po_double_validation_amount` **(monetary)** — Double validation amount
  > Minimum amount for which a double validation is required
- `inventory_valuation` **(selection)** — Valuation
  > Opções: `periodic` (Periodic (at closing)), `real_time` (Perpetual (at invoicing))
- `has_received_warning_stock_sms` **(boolean)** — Has Received Warning Stock Sms
- `background_image` **(binary)** — Home Menu Background Image
- `totals_below_sections` **(boolean)** — Add totals below sections
  > When ticked, totals and subtotals appear below the sections of the report.
- `account_last_return_cron_refresh` **(datetime)** — Account Last Return Cron Refresh
- `documents_approvals_settings` **(boolean)** — Documents Approvals Settings
- `appraisal_plan` **(boolean)** — Automatically Generate Appraisals
- `duration_after_recruitment` **(integer)** — Create an Appraisal after recruitment
- `duration_first_appraisal` **(integer)** — Create a first Appraisal after
- `duration_next_appraisal` **(integer)** — Create a second Appraisal after
- `recruitment_extract_show_ocr_option_selection` **(selection)** — Send mode on applicant attachments
  > Opções: `no_send` (Do not digitize), `manual_send` (Digitize on demand only), `auto_send` (Digitize automatically)
- `planning_self_unassign_days_before` **(integer)** — Days before shift for unassignment
  > Deadline in days for shift unassignment
- `days_to_purchase` **(float)** — Days to Purchase
  > Days needed to confirm a PO, define when a PO should be validated
- `portal_confirmation_sign` **(boolean)** — Online Signature
- `portal_confirmation_pay` **(boolean)** — Online Payment
- `prepayment_percent` **(float)** — Prepayment percentage
  > The percentage of the amount needed to be paid to confirm quotations.
- `quotation_validity_days` **(integer)** — Default Quotation Validity
  > Days between quotation proposal and expiration. 0 days means automatic expiration is disabled
- `sale_onboarding_payment_method` **(selection)** — Sale onboarding selected payment method
  > Opções: `digital_signature` (Sign online), `paypal` (PayPal), `stripe` (Stripe), `other` (Pay with another payment provider), `manual` (Manual Payment)
- `expense_extract_show_ocr_option_selection` **(selection)** — Send mode on expense attachments
  > Opções: `no_send` (Do not digitize), `manual_send` (Digitize on demand only), `auto_send` (Digitize automatically)
- `l10n_br_ie_code` **(char)** — IE
  > State Tax Identification Number. Should contain 9-14 digits.
- `l10n_br_im_code` **(char)** — IM
  > Municipal Tax Identification Number
- `l10n_br_nire_code` **(char)** — NIRE
  > State Commercial Identification Number. Should contain 11 digits.
- `manufacturing_period_to_display_year` **(integer)** — Number of columns for the yearly period to display in Master Production Schedule
- `manufacturing_period_to_display_month` **(integer)** — Number of columns for the monthly period to display in Master Production Schedule
- `manufacturing_period_to_display_week` **(integer)** — Number of columns for the weekly period to display in Master Production Schedule
- `manufacturing_period_to_display_day` **(integer)** — Number of columns for the daily period to display in Master Production Schedule
- `mrp_mps_show_starting_inventory` **(boolean)** — Display Starting Inventory
- `mrp_mps_show_demand_forecast` **(boolean)** — Display Demand Forecast
- `mrp_mps_show_actual_demand` **(boolean)** — Display Actual Demand
- `mrp_mps_show_indirect_demand` **(boolean)** — Display Indirect Demand
- `mrp_mps_show_indirect_actual_demand` **(boolean)** — Display Indirect Actual Demand
- `mrp_mps_show_to_replenish` **(boolean)** — Display To Replenish
- `mrp_mps_show_actual_replenishment` **(boolean)** — Display Actual Replenishment
- `mrp_mps_show_safety_stock` **(boolean)** — Display Safety Stock
- `mrp_mps_show_available_to_promise` **(boolean)** — Display Available to Promise
- `mrp_mps_show_actual_demand_year_minus_1` **(boolean)** — Display Actual Demand Last Year
- `mrp_mps_show_actual_demand_year_minus_2` **(boolean)** — Display Actual Demand Before Year
- `timesheet_mail_employee_allow` **(boolean)** — Employee Reminder
- `timesheet_mail_employee_delay` **(integer)** — Employee Reminder Days
- `timesheet_mail_employee_nextdate` **(datetime)** — Next scheduled date for employee reminder 🔒 readonly
- `timesheet_mail_allow` **(boolean)** — Approver Reminder
- `timesheet_mail_delay` **(integer)** — Approver Reminder Days
- `timesheet_mail_nextdate` **(datetime)** — Next scheduled date for approver reminder 🔒 readonly
- `extract_bank_statement_digitalization_mode` **(selection)** — Digitization mode on bank statements
  > Opções: `no_send` (Do not digitize), `auto_send` (Digitize automatically)
- `extract_in_invoice_digitalization_mode` **(selection)** — Digitization mode on vendor bills
  > Opções: `no_send` (Do not digitize), `manual_send` (Digitize on demand only), `auto_send` (Digitize automatically)
- `extract_out_invoice_digitalization_mode` **(selection)** — Digitization mode on customer invoices
  > Opções: `no_send` (Do not digitize), `manual_send` (Digitize on demand only), `auto_send` (Digitize automatically)
- `extract_single_line_per_tax` **(boolean)** — Single Invoice Line Per Tax
- `l10n_br_avatax_portal_email` **(char)** — Avatax Portal Email
- `l10n_br_avatax_api_identifier` **(char)** — Avalara Brazil API ID
- `l10n_br_avatax_api_key` **(char)** — Avalara Brazil API KEY
- `l10n_br_icms_rate` **(float)** — Simplified Regime ICMS Rate
- `l10n_br_is_icbs` **(boolean)** — Enable ICBS
  > Brazil: enable the fiscal reform.
- `timesheet_show_rates` **(boolean)** — Timesheet Show Rates
- `timesheet_show_leaderboard` **(boolean)** — Timesheet Show Leaderboard

## Relacionamentos

- `parent_id` **(many2one)** — Parent Company → `res.company`
- `child_ids` **(one2many)** — Branches → `res.company`
- `all_child_ids` **(one2many)** — All Child → `res.company`
- `parent_ids` **(many2many)** — Parent 🔒 readonly → `res.company`
- `root_id` **(many2one)** — Root 🔒 readonly → `res.company`
- `user_ids` **(many2many)** — Accepted Users → `res.users`
- `state_id` **(many2one)** — Fed. State → `res.country.state`
- `bank_ids` **(one2many)** — Banks → `res.partner.bank`
- `country_id` **(many2one)** — Country → `res.country`
- `paperformat_id` **(many2one)** — Paper format → `report.paperformat`
- `external_report_layout_id` **(many2one)** — Document Template → `ir.ui.view`
- `uninstalled_l10n_module_ids` **(many2many)** — Uninstalled L10N Module 🔒 readonly → `ir.module.module`
- `nomenclature_id` **(many2one)** — Nomenclature → `barcode.nomenclature`
- `resource_calendar_ids` **(one2many)** — Working Hours → `resource.calendar`
- `resource_calendar_id` **(many2one)** — Default Working Hours → `resource.calendar`
- `alias_domain_id` **(many2one)** — Email Domain → `mail.alias.domain`
- `signing_certificate_id` **(many2one)** — Signing Certificate → `certificate.certificate`
- `transfer_account_id` **(many2one)** — Inter-Banks Transfer Account → `account.account`
  > Intermediary account used when moving money from a liquidity account to another
- `default_cash_difference_income_account_id` **(many2one)** — Cash Difference Income → `account.account`
- `default_cash_difference_expense_account_id` **(many2one)** — Cash Difference Expense → `account.account`
- `account_journal_suspense_account_id` **(many2one)** — Journal Suspense Account → `account.account`
- `account_journal_early_pay_discount_gain_account_id` **(many2one)** — Cash Discount Write-Off Gain Account → `account.account`
- `account_journal_early_pay_discount_loss_account_id` **(many2one)** — Cash Discount Write-Off Loss Account → `account.account`
- `account_sale_tax_id` **(many2one)** — Default Sale Tax → `account.tax`
- `account_purchase_tax_id` **(many2one)** — Default Purchase Tax → `account.tax`
- `account_purchase_receipt_fiscal_position_id` **(many2one)** — Default Purchase Receipt Fiscal Position → `account.fiscal.position`
- `currency_exchange_journal_id` **(many2one)** — Exchange Gain or Loss Journal → `account.journal`
- `income_currency_exchange_account_id` **(many2one)** — Gain Exchange Rate Account → `account.account`
- `expense_currency_exchange_account_id` **(many2one)** — Loss Exchange Rate Account → `account.account`
- `bank_journal_ids` **(one2many)** — Bank Journals → `account.journal`
- `incoterm_id` **(many2one)** — Default incoterm → `account.incoterms`
  > International Commercial Terms are a series of predefined commercial terms used in international transactions.
- `batch_payment_sequence_id` **(many2one)** — Batch Payment Sequence 🔒 readonly → `ir.sequence`
- `account_opening_move_id` **(many2one)** — Opening Journal Entry → `account.move`
  > The journal entry containing the initial balance of all this company's accounts.
- `account_opening_journal_id` **(many2one)** — Opening Journal → `account.journal`
  > Journal where the opening entry of this company's accounting has been posted.
- `account_default_pos_receivable_account_id` **(many2one)** — Default PoS Receivable Account → `account.account`
- `expense_accrual_account_id` **(many2one)** — Expense Accrual Account → `account.account`
  > Account used to move the period of an expense
- `revenue_accrual_account_id` **(many2one)** — Revenue Accrual Account → `account.account`
  > Account used to move the period of a revenue
- `automatic_entry_default_journal_id` **(many2one)** — Automatic Entry Default Journal → `account.journal`
  > Journal used by default for moving the period of an entry
- `domestic_fiscal_position_id` **(many2one)** — Domestic Fiscal Position 🔒 readonly → `account.fiscal.position`
- `account_fiscal_country_id` **(many2one)** — Fiscal Country → `res.country`
  > The country to use the tax reports from for this company
- `account_enabled_tax_country_ids` **(many2many)** — l10n-used countries 🔒 readonly → `res.country`
  > Technical field containing the countries for which this company is using tax-related features(hence the ones for which l10n modules need to show tax-related fields).
- `tax_cash_basis_journal_id` **(many2one)** — Cash Basis Journal → `account.journal`
- `account_cash_basis_base_account_id` **(many2one)** — Base Tax Received Account → `account.account`
  > Account that will be set on lines created in cash basis journal entry and used to keep track of the tax base amount.
- `fiscal_position_ids` **(one2many)** — Fiscal Position → `account.fiscal.position`
- `multi_vat_foreign_country_ids` **(many2many)** — Foreign VAT countries 🔒 readonly → `res.country`
  > Countries for which the company has a VAT number
- `account_discount_income_allocation_id` **(many2one)** — Separate account for income discount → `account.account`
- `account_discount_expense_allocation_id` **(many2one)** — Separate account for expense discount → `account.account`
- `income_account_id` **(many2one)** — Income Account → `account.account`
  > This account will be used when validating a customer invoice.
- `expense_account_id` **(many2one)** — Expense Account → `account.account`
  > The expense is accounted for when a vendor bill is validated, except in anglo-saxon accounting with perpetual inventory valuation in which case the expense (Cost of Goods Sold account) is recognized at the customer invoice validation.
- `price_difference_account_id` **(many2one)** — Price Difference Account → `account.account`
  > During perpetual valuation, this account will hold the price difference between the standard price and the bill price.
- `internal_transit_location_id` **(many2one)** — Internal Transit Location → `stock.location`
- `stock_mail_confirmation_template_id` **(many2one)** — Email Template confirmation picking → `mail.template`
  > Email sent to the customer once the order is done.
- `website_id` **(many2one)** — Website 🔒 readonly → `website`
- `signing_user` **(many2one)** — Signing User → `res.users`
- `deferred_expense_journal_id` **(many2one)** — Deferred Expense Journal → `account.journal`
- `deferred_expense_account_id` **(many2one)** — Deferred Expense Account → `account.account`
- `deferred_revenue_journal_id` **(many2one)** — Deferred Revenue Journal → `account.journal`
- `deferred_revenue_account_id` **(many2one)** — Deferred Revenue Account → `account.account`
- `documents_employee_folder_id` **(many2one)** — Employees Folder → `documents.document`
- `documents_hr_contracts_tags` **(many2many)** — Documents Hr Contracts Tags → `documents.tag`
- `product_folder_id` **(many2one)** — Product Folder → `documents.document`
- `product_tag_ids` **(many2many)** — Product Tag → `documents.tag`
- `documents_project_folder_id` **(many2one)** — Project Folder → `documents.document`
- `expense_journal_id` **(many2one)** — Default Expense Journal → `account.journal`
  > The company's default journal used when an employee expense is created.
- `company_expense_allowed_payment_method_line_ids` **(many2many)** — Payment methods available for expenses paid by company → `account.payment.method.line`
- `account_stock_journal_id` **(many2one)** — Stock Journal → `account.journal`
- `account_stock_valuation_id` **(many2one)** — Stock Valuation Account → `account.account`
- `account_production_wip_account_id` **(many2one)** — Production WIP Account → `account.account`
- `account_production_wip_overhead_account_id` **(many2one)** — Production WIP Overhead Account → `account.account`
- `stock_sms_confirmation_template_id` **(many2one)** — SMS Template → `sms.template`
  > SMS sent to the customer once the order is delivered.
- `account_tax_return_journal_id` **(many2one)** — Journal → `account.journal`
- `account_revaluation_journal_id` **(many2one)** — Account Revaluation Journal → `account.journal`
- `account_revaluation_expense_provision_account_id` **(many2one)** — Expense Provision Account → `account.account`
- `account_revaluation_income_provision_account_id` **(many2one)** — Income Provision Account → `account.account`
- `account_tax_unit_ids` **(many2many)** — Tax Units → `account.tax.unit`
  > The tax units this company belongs to.
- `account_representative_id` **(many2one)** — Accounting Firm → `res.partner`
  > Specify an Accounting Firm that will act as a representative when exporting reports.
- `approvals_folder_id` **(many2one)** — Approvals Folder → `documents.document`
- `approvals_tag_ids` **(many2many)** — Approvals Tag → `documents.tag`
- `assessment_note_ids` **(one2many)** — Assessment Note → `hr.appraisal.note`
- `appraisal_confirm_mail_template` **(many2one)** — Appraisal Confirm Mail Template → `mail.template`
- `project_time_mode_id` **(many2one)** — Project Time Unit → `uom.uom`
  > This will set the unit of measure used in projects and tasks. If you use the timesheet linked to projects, don't forget to setup the right unit of measure in your employees.
- `timesheet_encode_uom_id` **(many2one)** — Timesheet Encoding Unit → `uom.uom`
- `internal_project_id` **(many2one)** — Internal Project → `project.project`
  > Default project value for timesheet generated from time off type.
- `subcontracting_location_id` **(many2one)** — Subcontracting Location → `stock.location`
- `sale_discount_product_id` **(many2one)** — Discount Product → `product.product`
  > Default product used for discounts
- `downpayment_account_id` **(many2one)** — Downpayment Account → `account.account`
  > This account will be used on Downpayment invoices.
- `stock_confirmation_wa_template_id` **(many2one)** — WhatsApp Template → `whatsapp.template`
  > Send WhatsApp to the customer once the order is delivered.
- `account_folder_id` **(many2one)** — Accounting Folder → `documents.document`
- `sale_order_template_id` **(many2one)** — Default Sale Template → `sale.order.template`
- `gain_account_id` **(many2one)** — Gain Account → `account.account`
  > Account used to write the journal item in case of gain while selling an asset
- `loss_account_id` **(many2one)** — Loss Account → `account.account`
  > Account used to write the journal item in case of loss while selling an asset
- `l10n_br_cnae_code_id` **(many2one)** — CNAE Code → `l10n_br.cnae.code`
  > Brazil: Main CNAE code registered with the government.

## Campos Calculados (readonly)

- `is_company_details_empty` **(boolean)** — Is Company Details Empty 🔒 readonly
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `company_registry_placeholder` **(char)** — Company Registry Placeholder 🔒 readonly
- `bounce_email` **(char)** — Bounce Email 🔒 readonly
- `bounce_formatted` **(char)** — Bounce 🔒 readonly
- `catchall_email` **(char)** — Catchall Email 🔒 readonly
- `catchall_formatted` **(char)** — Catchall 🔒 readonly
- `default_from_email` **(char)** — Default From 🔒 readonly
- `email_formatted` **(char)** — Formatted Email 🔒 readonly
- `user_fiscalyear_lock_date` **(date)** — User Fiscalyear Lock Date 🔒 readonly
- `user_tax_lock_date` **(date)** — User Tax Lock Date 🔒 readonly
- `user_sale_lock_date` **(date)** — User Sale Lock Date 🔒 readonly
- `user_purchase_lock_date` **(date)** — User Purchase Lock Date 🔒 readonly
- `user_hard_lock_date` **(date)** — User Hard Lock Date 🔒 readonly
- `account_fiscal_country_group_codes` **(json)** — Account Fiscal Country Group Codes 🔒 readonly
- `display_account_storno` **(boolean)** — Display Account Storno 🔒 readonly
- `force_restrictive_audit_trail` **(boolean)** — Force Audit Trail 🔒 readonly
- `company_vat_placeholder` **(char)** — Company Vat Placeholder 🔒 readonly
- `attendance_kiosk_url` **(char)** — Attendance Kiosk Url 🔒 readonly
- `account_display_representative_field` **(boolean)** — Account Display Representative Field 🔒 readonly
