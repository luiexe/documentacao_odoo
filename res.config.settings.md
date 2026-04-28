# Config Settings — `res.config.settings`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `currency_id` **(many2one)** — Currency ⚠️ obrigatório → `res.currency`
  > Main currency of the company.
- `account_price_include` **(selection)** — Default Sales Price Include ⚠️ obrigatório
  > Default on whether the sales price used on the product and invoices with this Company includes its taxes.
  > Opções: `tax_included` (Tax Included), `tax_excluded` (Tax Excluded)
- `fiscalyear_last_day` **(integer)** — Fiscalyear Last Day ⚠️ obrigatório
- `fiscalyear_last_month` **(selection)** — Fiscalyear Last Month ⚠️ obrigatório
  > Opções: `1` (January), `2` (February), `3` (March), `4` (April), `5` (May), `6` (June), `7` (July), `8` (August), `9` (September), `10` (October), `11` (November), `12` (December)
- `generate_deferred_expense_entries_method` **(selection)** — Generate Deferred Expense Entries ⚠️ obrigatório
  > Method used to generate deferred entries
  > Opções: `on_validation` (On bill validation), `manual` (Manually & Grouped)
- `deferred_expense_amount_computation_method` **(selection)** — Deferred Expense Based on ⚠️ obrigatório
  > Method used to compute the amount of deferred entries
  > Opções: `day` (Days), `month` (Months), `full_months` (Full Months)
- `generate_deferred_revenue_entries_method` **(selection)** — Generate Deferred Revenue Entries ⚠️ obrigatório
  > Method used to generate deferred entries
  > Opções: `on_validation` (On bill validation), `manual` (Manually & Grouped)
- `deferred_revenue_amount_computation_method` **(selection)** — Deferred Revenue Based on ⚠️ obrigatório
  > Method used to compute the amount of deferred entries
  > Opções: `day` (Days), `month` (Months), `full_months` (Full Months)
- `account_return_periodicity` **(selection)** — Periodicity ⚠️ obrigatório
  > Periodicity
  > Opções: `monthly` (Monthly), `2_months` (Every 2 months), `trimester` (Quarterly), `4_months` (Every 4 months), `semester` (Semi-annually), `year` (Annually), `fiscalyear` (Fiscal Year)
- `account_return_reminder_day` **(integer)** — Deadline ⚠️ obrigatório
- `timesheet_encode_method` **(selection)** — Encoding Method ⚠️ obrigatório
  > Opções: `hours` (Hours / Minutes), `days` (Days / Half-Days)
- `planning_generation_interval` **(integer)** — Rate Of Shift Generation ⚠️ obrigatório
- `default_picking_policy` **(selection)** — Picking Policy ⚠️ obrigatório
  > Opções: `direct` (Ship products as soon as available, with back orders), `one` (Ship all products at once)
- `valuation_method` **(selection)** — Inventory Valuation ⚠️ obrigatório
  > Opções: `periodic` (Periodic (at closing)), `real_time` (Perpetual (at invoicing))
- `cost_method` **(selection)** — Inventory Cost Method ⚠️ obrigatório
  > Opções: `standard` (Standard Price), `fifo` (First In First Out (FIFO)), `average` (Average Cost (AVCO))
- `inventory_period` **(selection)** — Inventory Period ⚠️ obrigatório
  > Opções: `manual` (Manual), `daily` (Daily), `monthly` (Monthly)
- `reminder_user_interval` **(selection)** — User Reminder Frequency ⚠️ obrigatório
  > Opções: `weeks` (after the end of the week), `months` (after the end of the month)
- `reminder_interval` **(selection)** — Approver Reminder Frequency ⚠️ obrigatório
  > Opções: `weeks` (after the end of the week), `months` (after the end of the month)
- `l10n_br_avalara_environment` **(selection)** — Avalara Brazil Environment ⚠️ obrigatório
  > Opções: `sandbox` (Sandbox), `production` (Production)
- `account_on_checkout` **(selection)** — Customer Accounts ⚠️ obrigatório
  > Opções: `optional` (Optional), `disabled` (Disabled), `mandatory` (Mandatory)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `web_app_name` **(char)** — Web App Name
- `module_base_import` **(boolean)** — Allow users to import data from CSV/XLS/XLSX/ODS files
- `module_google_calendar` **(boolean)** — Allow the users to synchronize their calendar  with Google Calendar
- `module_microsoft_calendar` **(boolean)** — Allow the users to synchronize their calendar with Outlook Calendar
- `module_mail_plugin` **(boolean)** — Allow integration with the mail plugins
- `module_auth_oauth` **(boolean)** — Use external authentication providers (OAuth)
- `module_auth_ldap` **(boolean)** — LDAP Authentication
- `module_account_inter_company_rules` **(boolean)** — Manage Inter Company
- `module_voip` **(boolean)** — Phone
- `module_web_unsplash` **(boolean)** — Unsplash Image Library
- `module_sms` **(boolean)** — SMS
- `module_partner_autocomplete` **(boolean)** — Partner Autocomplete
- `module_base_geolocalize` **(boolean)** — GeoLocalize
- `module_google_recaptcha` **(boolean)** — reCAPTCHA
- `module_website_cf_turnstile` **(boolean)** — Cloudflare Turnstile
- `module_google_address_autocomplete` **(boolean)** — Google Address Autocomplete
- `report_footer` **(html)** — Custom Report Footer
  > Footer text displayed at the bottom of all reports.
- `group_multi_currency` **(boolean)** — Multi-Currencies
  > Allows to work in a multi currency environment
- `show_effect` **(boolean)** — Show Effect
- `profiling_enabled_until` **(datetime)** — Profiling enabled until
- `geoloc_provider_googlemap_key` **(char)** — Google Map API Key
  > Visit https://developers.google.com/maps/documentation/geocoding/get-api-key for more information.
- `enable_recaptcha` **(boolean)** — Enable reCAPTCHA
- `recaptcha_public_key` **(char)** — Site Key
- `recaptcha_private_key` **(char)** — Secret Key
- `recaptcha_min_score` **(float)** — Minimum score
  > By default, should be one of 0.1, 0.3, 0.7, 0.9. 1.0 is very likely a good interaction, 0.0 is very likely a bot
- `map_box_token` **(char)** — Token Map Box
  > Necessary for some functionalities in the map view
- `external_email_server_default` **(boolean)** — Use Custom Email Servers
- `module_google_gmail` **(boolean)** — Support Gmail Authentication
- `module_microsoft_outlook` **(boolean)** — Support Outlook Authentication
- `restrict_template_rendering` **(boolean)** — Restrict Template Rendering
  > Users will still be able to render templates. However only Mail Template Editors will be able to create new dynamic templates or modify existing ones.
- `use_twilio_rtc_servers` **(boolean)** — Use Twilio ICE servers
  > If you want to use twilio as TURN/STUN server provider
- `twilio_account_sid` **(char)** — Account SID
- `twilio_account_token` **(char)** — Account Auth Token
- `use_sfu_server` **(boolean)** — Use SFU server
  > If you want to setup SFU server for large group calls.
- `sfu_server_url` **(char)** — SFU Server URL
- `sfu_server_key` **(char)** — SFU Server key
  > Base64 encoded key
- `email_primary_color` **(char)** — Email Button Text
- `email_secondary_color` **(char)** — Email Button Color
- `tenor_api_key` **(char)** — Tenor API key
  > Add a Tenor GIF API key to enable GIFs support. https://developers.google.com/tenor/guides/quickstart#setup
- `google_translate_api_key` **(char)** — Message Translation API Key
  > A valid Google API key is required to enable message translation. https://cloud.google.com/translate/docs/setup
- `unsplash_access_key` **(char)** — Access Key
- `unsplash_app_id` **(char)** — Application ID
- `openai_key_enabled` **(boolean)** — Enable custom OpenAI API key
- `openai_key` **(char)** — OpenAI API key
- `google_key_enabled` **(boolean)** — Enable custom Google API key
- `google_key` **(char)** — Google AI API key
- `group_analytic_accounting` **(boolean)** — Analytic Accounting
- `auth_signup_reset_password` **(boolean)** — Enable password reset from Login page
- `auth_signup_uninvited` **(selection)** — Customer Account
  > Opções: `b2b` (On invitation), `b2c` (Free sign up)
- `auth_totp_enforce` **(boolean)** — Enforce two-factor authentication
- `auth_totp_policy` **(selection)** — Two-factor authentication enforcing policy
  > Opções: `employee_required` (Employees only), `all_required` (All users)
- `google_gmail_client_identifier` **(char)** — Gmail Client Id
- `google_gmail_client_secret` **(char)** — Gmail Client Secret
- `microsoft_outlook_client_identifier` **(char)** — Outlook Client Id
- `microsoft_outlook_client_secret` **(char)** — Outlook Client Secret
- `group_uom` **(boolean)** — Units of Measure & Packagings
- `group_product_variant` **(boolean)** — Variants
- `module_loyalty` **(boolean)** — Promotions, Coupons, Gift Card & Loyalty Program
- `group_product_pricelist` **(boolean)** — Pricelists
- `product_weight_in_lbs` **(selection)** — Weight unit of measure
  > Opções: `0` (Kilograms (kg)), `1` (Pounds (lb))
- `product_volume_volume_in_cubic_feet` **(selection)** — Volume unit of measure
  > Opções: `0` (Cubic Meters (m³)), `1` (Cubic Feet (ft³))
- `disable_redirect_firebase_dynamic_link` **(boolean)** — Disable link redirection to mobile app
  > Check this if dynamic mobile-app detection links cause problems for your installation. This will stop the automatic wrapping of links inside outbound emails. The links will always open in a normal browser, even for users who have the Android/iOS app installed.
- `enable_ocn` **(boolean)** — Push Notifications
- `portal_allow_api_keys` **(boolean)** — Customer API Keys
- `barcodelookup_api_key` **(char)** — API key
  > Barcode Lookup API Key for create product from barcode.
- `snailmail_color` **(boolean)** — Print In Color
- `snailmail_cover` **(boolean)** — Add a Cover Page
- `snailmail_duplex` **(boolean)** — Print Both sides
- `digest_emails` **(boolean)** — Digest Emails
- `sign_terms` **(html)** — Sign Terms & Conditions
- `sign_terms_html` **(html)** — Sign Terms & Conditions as a Web page
- `sign_terms_type` **(selection)** — Sign Terms & Conditions format
  > Terms in Email - The text will be displayed at the bottom of every signature request email.          Terms as Web Page - A link will be pasted at the bottom of every signature request email, leading to your content.         
  > Opções: `plain` (Terms in Email), `html` (Terms as Web Page)
- `use_sign_terms` **(boolean)** — Sign Default Terms & Conditions
- `group_manage_template_access` **(boolean)** — Manage template access
- `module_sign_itsme` **(boolean)** — Identify with itsme®
- `module_sign_emsigner` **(boolean)** — Sign with Aadhaar eSign
- `chart_template` **(selection)** — Chart Template
  > Opções: `br` (🇧🇷 Brazil), `generic_coa` (Generic Chart of Accounts), `ae` (🇦🇪 United Arab Emirates), `ar_ri` (🇦🇷 Argentina - Argentine Generic Chart of Accounts for Registered Accountants), `ar_base` (🇦🇷 Argentina - Generic Chart of Accounts Argentina Single Taxpayer / Basis), `ar_ex` (🇦🇷 Argentina - Argentine Generic Chart of Accounts for Exempt Individuals), `at` (🇦🇹 Austria), `au` (🇦🇺 Australia), `bd` (🇧🇩 Bangladesh), `be_comp` (🇧🇪 Belgium - Companies), `be_asso` (🇧🇪 Belgium - Associations and Foundations), `bf` (🇧🇫 Burkina Faso - SYSCOHADA for Companies), `bf_syscebnl` (🇧🇫 Burkina Faso - SYSCEBNL for Associations), `bg` (🇧🇬 Bulgaria), `bh` (🇧🇭 Bahrain), `bj` (🇧🇯 Benin - SYSCOHADA for Companies), `bj_syscebnl` (🇧🇯 Benin - SYSCEBNL for Associations), `bo` (🇧🇴 Bolivia), `ca_2023` (🇨🇦 Canada), `cd` (🇨🇩 Congo (DRC) - SYSCOHADA for Companies), `cd_syscebnl` (🇨🇩 Congo (DRC) - SYSCEBNL for Associations), `cf` (🇨🇫 Central African Republic - SYSCOHADA for Companies), `cf_syscebnl` (🇨🇫 Central African Republic - SYSCEBNL for Associations), `cg` (🇨🇬 Congo (Republic) - SYSCOHADA for Companies), `cg_syscebnl` (🇨🇬 Congo (Republic) - SYSCEBNL for Associations), `ch` (🇨🇭 Switzerland), `ci` (🇨🇮 Côte d'Ivoire - SYSCOHADA for Companies), `ci_syscebnl` (🇨🇮 Côte d'Ivoire - SYSCEBNL for Associations), `cl` (🇨🇱 Chile), `cm` (🇨🇲 Cameroon - SYSCOHADA for Companies), `cm_syscebnl` (🇨🇲 Cameroon - SYSCEBNL for Associations), `cn` (🇨🇳 China - Accounting Standards for Small Business Enterprises), `cn_large_bis` (🇨🇳 China - Accounting Standards for Business Enterprises), `co` (🇨🇴 Colombia), `cr` (🇨🇷 Costa Rica), `cy` (🇨🇾 Cyprus), `cz` (🇨🇿 Czech Republic), `de_skr03` (🇩🇪 Germany - German Chart of Accounts SKR03), `de_skr04` (🇩🇪 Germany - German chart of accounts SKR04), `dk` (🇩🇰 Denmark), `do` (🇩🇴 Dominican Republic), `dz` (🇩🇿 Algeria), `ec` (🇪🇨 Ecuador), `ee` (🇪🇪 Estonia), `eg` (🇪🇬 Egypt), `es_pymes` (🇪🇸 Spain - SMEs (2008)), `es_assec` (🇪🇸 Spain - Non-profit entities (2008)), `es_canary_assoc` (🇪🇸 Spain - Canary Islands - PGCE non-profit entities (2008)), `es_canary_full` (🇪🇸 Spain - Canary Islands - Complete (2008)), `es_canary_pymes` (🇪🇸 Spain - Canary Islands - SMEs (2008)), `es_coop_full` (🇪🇸 Spain - Cooperatives - Complete (2008)), `es_coop_pymes` (🇪🇸 Spain - Cooperatives - SMEs (2008)), `es_full` (🇪🇸 Spain - Complete (2008)), `et` (🇪🇹 Ethiopia), `fi` (🇫🇮 Finland), `fr` (🇫🇷 France), `mc` (🇲🇨 Monaco), `ga` (🇬🇦 Gabon - SYSCOHADA for Companies), `ga_syscebnl` (🇬🇦 Gabon - SYSCEBNL for Associations), `gn` (🇬🇳 Guinea - SYSCOHADA for Companies), `gn_syscebnl` (🇬🇳 Guinea - SYSCEBNL for Associations), `gq` (🇬🇶 Equatorial Guinea - SYSCOHADA for Companies), `gq_syscebnl` (🇬🇶 Equatorial Guinea - SYSCEBNL for Associations), `gr` (🇬🇷 Greece), `gt` (🇬🇹 Guatemala), `gw` (🇬🇼 Guinea-Bissau - SYSCOHADA for Companies), `gw_syscebnl` (🇬🇼 Guinea-Bissau - SYSCEBNL for Associations), `hk` (🇭🇰 Hong Kong), `hn` (🇭🇳 Honduras), `hr` (🇭🇷 Croatia), `hr_kuna` (🇭🇷 Croatia - RRIF-ov računski plan za poduzetnike), `hu` (🇭🇺 Hungary), `id` (🇮🇩 Indonesia), `ie` (🇮🇪 Ireland), `il` (🇮🇱 Israel), `in` (🇮🇳 India), `iq` (🇮🇶 Iraq), `it` (🇮🇹 Italy), `jo_standard` (🇯🇴 Jordan), `jp` (🇯🇵 Japan), `ke` (🇰🇪 Kenya), `kh` (🇰🇭 Cambodia), `km` (🇰🇲 Comoros - SYSCOHADA for Companies), `km_syscebnl` (🇰🇲 Comoros - SYSCEBNL for Associations), `kr` (🇰🇷 South Korea), `kw` (🇰🇼 Kuwait), `kz` (🇰🇿 Kazakhstan), `lb` (🇱🇧 Lebanon), `lk` (🇱🇰 Sri Lanka), `lt` (🇱🇹 Lithuania), `lu` (🇱🇺 Luxembourg), `lv` (🇱🇻 Latvia), `ma` (🇲🇦 Morocco), `ml` (🇲🇱 Mali - SYSCOHADA for Companies), `ml_syscebnl` (🇲🇱 Mali - SYSCEBNL for Associations), `mn` (🇲🇳 Mongolia), `mr` (🇲🇷 Mauritania), `mt` (🇲🇹 Malta), `mu` (🇲🇺 Mauritius), `mx` (🇲🇽 Mexico), `my` (🇲🇾 Malaysia), `mz` (🇲🇿 Mozambique), `ne` (🇳🇪 Niger - SYSCOHADA for Companies), `ne_syscebnl` (🇳🇪 Niger - SYSCEBNL for Associations), `ng` (🇳🇬 Nigeria), `nl` (🇳🇱 Netherlands), `no` (🇳🇴 Norway), `nz` (🇳🇿 New Zealand), `om` (🇴🇲 Oman), `pa` (🇵🇦 Panama), `pe` (🇵🇪 Peru), `ph` (🇵🇭 Philippines), `pk` (🇵🇰 Pakistan), `pl` (🇵🇱 Poland), `pt` (🇵🇹 Portugal), `qa` (🇶🇦 Qatar), `ro` (🇷🇴 Romania), `rs` (🇷🇸 Serbia), `rw` (🇷🇼 Rwanda), `sa` (🇸🇦 Saudi Arabia), `se` (🇸🇪 Sweden), `se_K2` (🇸🇪 Sweden - Swedish BAS Chart of Account complete K2), `se_K3` (🇸🇪 Sweden - Swedish BAS Chart of Account complete K3), `sg` (🇸🇬 Singapore), `si` (🇸🇮 Slovenia), `sk` (🇸🇰 Slovakia), `sn` (🇸🇳 Senegal - SYSCOHADA for Companies), `sn_syscebnl` (🇸🇳 Senegal - SYSCEBNL for Associations), `syscebnl` (SYSCEBNL), `syscohada` (SYSCOHADA - Revised), `td` (🇹🇩 Chad - SYSCOHADA for Companies), `td_syscebnl` (🇹🇩 Chad - SYSCEBNL for Associations), `tg` (🇹🇬 Togo - SYSCOHADA for Companies), `tg_syscebnl` (🇹🇬 Togo - SYSCEBNL for Associations), `th` (🇹🇭 Thailand), `tn` (🇹🇳 Tunisia), `tr` (🇹🇷 Türkiye), `tw` (🇹🇼 Taiwan), `tz` (🇹🇿 Tanzania), `ua_psbo` (🇺🇦 Ukraine - IFRS Chart of Accounts), `ug` (🇺🇬 Uganda - Uganda Generic Chart of Accounts), `uk` (🇬🇧 United Kingdom), `xi` (🇽🇮 Northern Ireland), `us` (🇺🇸 United States), `uy` (🇺🇾 Uruguay - Uruguayan Generic Chart of Accounts), `uz` (🇺🇿 Uzbekistan), `ve` (🇻🇪 Venezuela), `vn` (🇻🇳 Vietnam), `za` (🇿🇦 South Africa), `zm` (🇿🇲 Zambia)
- `tax_calculation_rounding_method` **(selection)** — Tax calculation rounding method
  > Opções: `round_globally` (Round per Tax), `round_per_line` (Round per Line)
- `module_account_accountant` **(boolean)** — Accounting
- `group_cash_rounding` **(boolean)** — Cash Rounding
- `show_sale_receipts` **(boolean)** — Sale Receipt
- `module_account_budget` **(boolean)** — Budget Management
- `module_account_payment` **(boolean)** — Invoice Online Payment
- `module_account_reports` **(boolean)** — Dynamic Reports
- `module_account_check_printing` **(boolean)** — Allow check printing and deposits
- `module_account_batch_payment` **(boolean)** — Use batch payments
  > This allows you grouping payments into a single batch and eases the reconciliation process. -This installs the account_batch_payment module.
- `module_account_iso20022` **(boolean)** — SEPA Credit Transfer / ISO20022
- `module_account_sepa_direct_debit` **(boolean)** — Use SEPA Direct Debit
- `module_account_bank_statement_import_qif` **(boolean)** — Import .qif files
- `module_currency_rate_live` **(boolean)** — Automatic Currency Rates
- `module_account_intrastat` **(boolean)** — Intrastat
- `module_product_margin` **(boolean)** — Allow Product Margin
- `module_account_extract` **(boolean)** — Document Digitization
- `module_account_invoice_extract` **(boolean)** — Invoice Digitization
- `module_account_bank_statement_extract` **(boolean)** — Bank Statement Digitization
- `module_snailmail_account` **(boolean)** — Snailmail
- `module_account_peppol` **(boolean)** — PEPPOL Invoicing
- `tax_exigibility` **(boolean)** — Cash Basis
- `qr_code` **(boolean)** — Display SEPA QR-code
- `link_qr_code` **(boolean)** — Display Link QR-code
- `invoice_terms` **(html)** — Terms & Conditions
- `invoice_terms_html` **(html)** — Terms & Conditions as a Web page
- `terms_type` **(selection)** — Terms & Conditions format
  > Opções: `plain` (Add a Note), `html` (Add a link to a Web Page)
- `display_invoice_amount_total_words` **(boolean)** — Total amount of invoice in letters
- `display_invoice_tax_company_currency` **(boolean)** — Taxes in company currency
- `use_invoice_terms` **(boolean)** — Default Terms & Conditions
- `account_use_credit_limit` **(boolean)** — Sales Credit Limit
  > Enable the use of credit limit on partners.
- `account_default_credit_limit` **(monetary)** — Default Credit Limit
  > This is the default credit limit that will be used on partners that do not have a specific limit on them.
- `account_storno` **(boolean)** — Storno accounting
- `group_sale_delivery_address` **(boolean)** — Customer Addresses
- `quick_edit_mode` **(selection)** — Quick encoding
  > Opções: `out_invoices` (Customer Invoices), `in_invoices` (Vendor Bills), `out_and_in_invoices` (Customer Invoices and Vendor Bills)
- `restrictive_audit_trail` **(boolean)** — Restricted Audit Trail
  > Enable this option to prevent deletion of journal item related logs
- `force_restrictive_audit_trail` **(boolean)** — Forced Audit Trail
- `autopost_bills` **(boolean)** — Auto-validate bills
- `group_use_lead` **(boolean)** — Leads
- `group_use_recurring_revenues` **(boolean)** — Recurring Revenues
- `is_membership_multi` **(boolean)** — Multi Teams
- `module_partnership` **(boolean)** — Membership / Partnership
- `crm_use_auto_assignment` **(boolean)** — Rule-Based Assignment
- `crm_auto_assignment_action` **(selection)** — Auto Assignment Action
  > Manual assign allow to trigger assignment from team form view using an action button. Automatic configures a cron running repeatedly assignment in all teams.
  > Opções: `manual` (Manually), `auto` (Repeatedly)
- `crm_auto_assignment_interval_type` **(selection)** — Auto Assignment Interval Unit
  > Interval type between each cron run (e.g. each 2 days or each 2 hours)
  > Opções: `minutes` (Minutes), `hours` (Hours), `days` (Days), `weeks` (Weeks)
- `crm_auto_assignment_interval_number` **(integer)** — Repeat every
  > Number of interval type between each cron run (e.g. each 2 days or each 4 days)
- `crm_auto_assignment_run_datetime` **(datetime)** — Auto Assignment Next Execution Date
- `module_crm_iap_mine` **(boolean)** — Generate new leads based on their country, industries, size, etc.
- `module_crm_iap_enrich` **(boolean)** — Enrich your leads automatically with company data based on their email address.
- `module_website_crm_iap_reveal` **(boolean)** — Create Leads/Opportunities from your website's traffic
- `lead_enrich_auto` **(selection)** — Enrich lead automatically
  > Opções: `manual` (Enrich leads on demand only), `auto` (Enrich all leads automatically)
- `lead_mining_in_pipeline` **(boolean)** — Create a lead mining request directly from the opportunity pipeline.
- `predictive_lead_scoring_start_date` **(date)** — Lead Scoring Starting Date
- `predictive_lead_scoring_start_date_str` **(char)** — Lead Scoring Starting Date in String
- `predictive_lead_scoring_fields_str` **(char)** — Lead Scoring Frequency Fields in String
- `deletion_delay` **(integer)** — Deletion Delay
  > Delay after permanent deletion of the document in the trash (days)
- `module_hr_presence` **(boolean)** — Advanced Presence Control
- `module_hr_skills` **(boolean)** — Skills Management
- `hr_presence_control_login` **(boolean)** — Based on user status in system
- `hr_presence_control_email` **(boolean)** — Based on number of emails sent
- `hr_presence_control_ip` **(boolean)** — Based on IP Address
- `module_hr_attendance` **(boolean)** — Based on attendances
- `hr_presence_control_email_amount` **(integer)** — # emails to send
- `hr_presence_control_ip_list` **(char)** — Valid IP addresses
- `contract_expiration_notice_period` **(integer)** — Contract Expiry Notice Period
- `work_permit_expiration_notice_period` **(integer)** — Work Permit Expiry Notice Period
- `group_mass_mailing_campaign` **(boolean)** — Mailing Campaigns
  > This is useful if your marketing campaigns are composed of several emails
- `mass_mailing_outgoing_mail_server` **(boolean)** — Dedicated Server
  > Use a specific mail server in priority. Otherwise Odoo relies on the first outgoing mail server available (based on their sequencing) as it does for normal mails.
- `show_blacklist_buttons` **(boolean)** — Blacklist Option when Unsubscribing
  > Allow the recipient to manage themselves their state in the blacklist via the unsubscription page.
- `mass_mailing_reports` **(boolean)** — 24H Stat Mailing Reports
  > Check how well your mailing is doing a day after it has been sent.
- `mass_mailing_split_contact_name` **(boolean)** — Split First and Last Name
  > Separate Mailing Contact Names into two fields
- `module_hr_timesheet` **(boolean)** — Task Logs
- `group_project_stages` **(boolean)** — Project Stages
- `module_product_expiry` **(boolean)** — Expiration Dates
  > Track following dates on lots & serial numbers: best before, removal, end of life, alert.   Such dates are set automatically at lot/serial number creation based on values set on the product (in days).
- `group_stock_production_lot` **(boolean)** — Lots & Serial Numbers
- `group_stock_lot_print_gs1` **(boolean)** — Print GS1 Barcodes for Lots & Serial Numbers
- `group_lot_on_delivery_slip` **(boolean)** — Display Lots & Serial Numbers on Delivery Slips
- `group_stock_tracking_lot` **(boolean)** — Packages
- `group_stock_tracking_owner` **(boolean)** — Consignment
- `group_stock_adv_location` **(boolean)** — Multi-Step Routes
  > Add and customize route operations to process product moves in your warehouse(s): e.g. unload > quality control > stock for incoming products, pick > pack > ship for outgoing products.   You can also set putaway strategies on warehouse locations in order to send incoming products into specific child locations straight away (e.g. specific bins, racks).
- `group_warning_stock` **(boolean)** — Warnings for Stock
- `group_stock_sign_delivery` **(boolean)** — Signature
- `module_stock_picking_batch` **(boolean)** — Batch, Wave & Cluster Transfers
- `module_stock_barcode` **(boolean)** — Barcode Scanner
- `module_stock_barcode_barcodelookup` **(boolean)** — Stock Barcode Database
- `stock_move_email_validation` **(boolean)** — Email Confirmation picking
- `module_stock_sms` **(boolean)** — SMS Confirmation
- `module_delivery` **(boolean)** — Delivery Methods
- `module_delivery_dhl` **(boolean)** — DHL Express Connector
- `module_delivery_fedex_rest` **(boolean)** — FedEx Connector
- `module_delivery_ups_rest` **(boolean)** — UPS Connector
- `module_delivery_usps_rest` **(boolean)** — USPS Connector
- `module_delivery_bpost` **(boolean)** — bpost Connector
- `module_delivery_easypost` **(boolean)** — Easypost Connector
- `module_delivery_sendcloud` **(boolean)** — Sendcloud Connector
- `module_delivery_shiprocket` **(boolean)** — Shiprocket Connector
- `module_delivery_starshipit` **(boolean)** — Starshipit Connector
- `module_delivery_envia` **(boolean)** — Envia.com Connector
- `module_quality_control` **(boolean)** — Quality
- `module_quality_control_worksheet` **(boolean)** — Quality Worksheet
- `group_stock_multi_locations` **(boolean)** — Storage Locations
  > Store products in specific locations of your warehouse (e.g. bins, racks) and to track inventory accordingly.
- `annual_inventory_month` **(selection)** — Annual Inventory Month
  > Annual inventory month for products not in a location with a cyclic inventory date. Set to no month if no automatic annual inventory.
  > Opções: `1` (January), `2` (February), `3` (March), `4` (April), `5` (May), `6` (June), `7` (July), `8` (August), `9` (September), `10` (October), `11` (November), `12` (December)
- `annual_inventory_day` **(integer)** — Day of the month
  > Day of the month when the annual inventory should occur. If zero or negative, then the first day of the month will be selected instead.         If greater than the last day of a month, then the last day of the month will be selected instead.
- `group_stock_reception_report` **(boolean)** — Reception Report
- `module_stock_dropshipping` **(boolean)** — Dropshipping
- `barcode_separator` **(char)** — Separator
  > Character(s) used to separate data contained within an aggregate barcode (i.e. a barcode containing multiple barcode encodings)
- `module_stock_fleet` **(boolean)** — Dispatch Management System
- `replenish_on_order` **(boolean)** — Replenish on Order (MTO)
- `stock_text_confirmation` **(boolean)** — Stock Text Validation with stock move
- `stock_confirmation_type` **(selection)** — Stock Text Validation type
  > Opções: `sms` (SMS), `whatsapp` (Whatsapp)
- `horizon_days` **(float)** — Replenishment Horizon
  > Configure your horizon to trigger reordering rules earlier to get                                 a head start on replenishment and avoid delays, or trigger it just-in-time                                 ('0 days') to avoid overstocking.
- `website_name` **(char)** — Website Name
- `website_domain` **(char)** — Website Domain
  > E.g. https://www.mydomain.com
- `website_homepage_url` **(char)** — Homepage Url
  > E.g. /contactus or /shop
- `website_logo` **(binary)** — Website Logo
  > Display this logo on the website.
- `website_default_lang_code` **(char)** — Default language code
  > This field is used to set/get locales for user
- `shared_user_account` **(boolean)** — Shared Customer Accounts
- `website_cookies_bar` **(boolean)** — Cookies Bar
  > Display a customizable cookies bar on your website.
- `website_block_third_party_domains` **(boolean)** — Block 3rd-party domains
  > Block 3rd-party domains that may track users (YouTube, Google Maps, etc.).
- `google_analytics_key` **(char)** — Google Analytics Key
- `google_search_console` **(char)** — Google Search Console Key
  > Google key, or Enable to access first reply
- `plausible_shared_key` **(char)** — Plausible auth Key
- `plausible_site` **(char)** — Plausible Site (e.g. domain.com)
- `cdn_activated` **(boolean)** — Content Delivery Network (CDN)
- `cdn_url` **(char)** — CDN Base URL
- `cdn_filters` **(text)** — CDN Filters
  > URL matching those filters will be rewritten using the CDN Base URL
- `favicon` **(binary)** — Favicon
  > This field holds the image used to display a favicon on the website.
- `social_default_image` **(binary)** — Default Social Share Image
  > If set, replaces the website logo as the default social share image.
- `group_multi_website` **(boolean)** — Multi-website
- `has_google_analytics` **(boolean)** — Google Analytics
- `has_google_search_console` **(boolean)** — Google Search Console
- `has_default_share_image` **(boolean)** — Use a image by default for sharing
- `has_plausible_shared_key` **(boolean)** — Plausible Analytics
- `module_website_livechat` **(boolean)** — Module Website Livechat
- `use_anglo_saxon` **(boolean)** — Anglo-Saxon Accounting
- `invoicing_switch_threshold` **(date)** — Invoicing Switch Threshold
  > Every payment and invoice before this date will receive the 'From Invoicing' status, hiding all the accounting entries related to it. Use this option after installing Accounting if you were using only Invoicing before, before importing all your actual accounting data in to Odoo.
- `group_fiscal_year` **(boolean)** — Fiscal Years
- `predict_bill_product` **(boolean)** — Predict Bill Product
- `sign_invoice` **(boolean)** — Authorized Signatory on invoice
- `module_account_auto_transfer` **(boolean)** — Enable Auto Transfer
- `pay_invoices_online` **(boolean)** — Pay Invoices Online
- `vat_check_vies` **(boolean)** — Verify VAT Numbers
- `currency_interval_unit` **(selection)** — Interval Unit
  > Opções: `manually` (Manually), `daily` (Daily), `weekly` (Weekly), `monthly` (Monthly)
- `currency_provider` **(selection)** — Service Provider
  > Opções: `ecb` (European Central Bank), `xe_com` (xe.com), `cbuae` ([AE] Central Bank of the UAE), `bnb` ([BG] Bulgaria National Bank), `bbr` ([BR] Central Bank of Brazil), `boc` ([CA] Bank of Canada), `fta` ([CH] Federal Tax Administration of Switzerland), `mindicador` ([CL] Central Bank of Chile via mindicador.cl), `banrepco` ([CO] Bank of the Republic), `cu` ([CU] Central Bank of Cuba), `cnb` ([CZ] Czech National Bank), `cbegy` ([EG] Central Bank of Egypt), `nbg` ([GE] National Bank of Georgia), `banguat` ([GT] Bank of Guatemala), `mnb` ([HU] Magyar Nemzeti Bank), `bi` ([ID] Bank Indonesia), `boi` ([IT] Bank of Italy), `nbkz` ([KZ] National Bank of Kazakhstan), `banxico` ([MX] Bank of Mexico), `bnm` ([MY] Bank Negara Malaysia), `bcrp` ([PE] SUNAT (replaces Bank of Peru)), `nbp` ([PL] National Bank of Poland), `bnr` ([RO] National Bank of Romania), `srb` ([SE] Sveriges Riksbank), `bsi` ([SI] Bank of Slovenia), `bot` ([TH] Bank of Thailand), `tcmb` ([TR] Central Bank of the Republic of Türkiye), `hmrc` ([UK] HM Revenue & Customs), `bcu` ([UY] Uruguayan Central Bank), `cbu` ([UZ] Central Bank of Uzbekistan)
- `currency_next_execution_date` **(date)** — Next Execution Date
- `documents_hr_settings` **(boolean)** — Human Resources
- `employee_subfolders` **(char)** — Employees Subfolder
  > Comma separated string of folder names that need to be created under each employee folder.
- `documents_product_settings` **(boolean)** — Product
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
- `hr_expense_alias_prefix` **(char)** — Default Alias Name for Expenses
- `hr_expense_use_mailgateway` **(boolean)** — Let your employees record expenses by email
- `module_hr_payroll_expense` **(boolean)** — Reimburse Expenses in Payslip
- `module_hr_expense_extract` **(boolean)** — Send bills to OCR to generate expenses
- `module_hr_expense_stripe` **(boolean)** — Link your stripe issuing account to manage company credit cards for your employees through Odoo
- `module_website_hr_recruitment` **(boolean)** — Online Posting
- `module_hr_recruitment_survey` **(boolean)** — Interview Forms
- `module_hr_recruitment_extract` **(boolean)** — Send CV to OCR to fill applications
- `group_mrp_byproducts` **(boolean)** — By-Products
- `module_mrp_mps` **(boolean)** — Master Production Schedule
- `module_mrp_plm` **(boolean)** — Product Lifecycle Management (PLM)
- `module_mrp_subcontracting` **(boolean)** — Subcontracting
- `group_mrp_routings` **(boolean)** — MRP Work Orders
- `group_unlocked_by_default` **(boolean)** — Unlock Manufacturing Orders
- `group_mrp_reception_report` **(boolean)** — Allocation Report for Manufacturing Orders
- `group_mrp_workorder_dependencies` **(boolean)** — Work Order Dependencies
- `lock_confirmed_po` **(boolean)** — Lock Confirmed Orders
- `po_lock` **(selection)** — Purchase Order Modification *
  > Purchase Order Modification used when you want to purchase order editable after confirm
  > Opções: `edit` (Allow to edit purchase orders), `lock` (Confirmed purchase orders are not editable)
- `po_order_approval` **(boolean)** — Purchase Order Approval
- `po_double_validation` **(selection)** — Levels of Approvals *
  > Provide a double validation mechanism for purchases
  > Opções: `one_step` (Confirm purchase orders in one step), `two_step` (Get 2 levels of approvals to confirm a purchase order)
- `po_double_validation_amount` **(monetary)** — Minimum Amount
  > Minimum amount for which a double validation is required
- `group_warning_purchase` **(boolean)** — Purchase Warnings
- `module_account_3way_match` **(boolean)** — 3-way matching: purchases, receptions and bills
- `module_purchase_requisition` **(boolean)** — Purchase Agreements
- `module_purchase_product_matrix` **(boolean)** — Purchase Grid Entry
- `group_send_reminder` **(boolean)** — Receipt Reminder
  > Allow automatically send email to remind your vendor the receipt date
- `module_stock_landed_costs` **(boolean)** — Landed Costs
  > Affect landed costs on reception operations and split them among products to update their cost price.
- `group_lot_on_invoice` **(boolean)** — Display Lots & Serial Numbers on Invoices
- `stock_barcode_mute_sound_notifications` **(boolean)** — Mute Barcode application sounds
- `barcode_max_time_between_keys_in_ms` **(integer)** — Max time between each key
  > Maximum delay between each key in ms (100 ms by default)
- `barcode_rfid_batch_time` **(integer)** — RFID Timer
- `barcode_separator_regex` **(char)** — Multiscan Separator
  > This regex is used in the Barcode application to separate individual barcodes when an aggregate barcode (i.e. single barcode consisting of multiple barcode encodings) is scanned.
- `module_whatsapp_stock` **(boolean)** — WhatsApp Confirmation
- `totals_below_sections` **(boolean)** — Add totals below sections
  > When ticked, totals and subtotals appear below the sections of the report.
- `documents_approvals_settings` **(boolean)** — Approvals
- `appraisal_plan` **(boolean)** — Automatically Generate Appraisals
- `duration_after_recruitment` **(integer)** — Create an Appraisal after recruitment
- `duration_first_appraisal` **(integer)** — Create a first Appraisal after
- `duration_next_appraisal` **(integer)** — Create a second Appraisal after
- `module_hr_appraisal_survey` **(boolean)** — 360 Feedback
- `recruitment_extract_show_ocr_option_selection` **(selection)** — Recruitment processing option
  > Opções: `no_send` (Do not digitize), `manual_send` (Digitize on demand only), `auto_send` (Digitize automatically)
- `module_project_timesheet_holidays` **(boolean)** — Time Off
- `reminder_user_allow` **(boolean)** — Employee Reminder
- `reminder_allow` **(boolean)** — Approver Reminder
- `group_mrp_wo_tablet_timer` **(boolean)** — Timer
- `group_mrp_wo_shop_floor` **(boolean)** — Shop Floor
- `wo_shop_floor_maximum_card_count` **(integer)** — Maximum number of cards per page
- `module_project_forecast` **(boolean)** — Project Planning
- `planning_employee_unavailabilities` **(selection)** — Employee Unavailabilities
  > Opções: `switch` (Switch shifts with other employees), `unassign` (Unassign themselves from shifts)
- `planning_self_unassign_days_before` **(integer)** — Days before shift for unassignment
  > Deadline in days for shift unassignment
- `days_to_purchase` **(float)** — Days to Purchase
  > Days needed to confirm a PO, define when a PO should be validated
- `is_installed_sale` **(boolean)** — Is the Sale Module Installed
- `default_invoice_policy` **(selection)** — Invoicing Policy
  > Opções: `order` (Invoice what is ordered), `delivery` (Invoice what is delivered)
- `group_auto_done_setting` **(boolean)** — Lock Confirmed Sales
- `group_discount_per_so_line` **(boolean)** — Discounts
- `group_proforma_sales` **(boolean)** — Pro-Forma Invoice
  > Allows you to send pro-forma invoice.
- `group_warning_sale` **(boolean)** — Sale Order Warnings
- `automatic_invoice` **(boolean)** — Automatic Invoice
  > The invoice is generated automatically and available in the customer portal when the transaction is confirmed by the payment provider. The invoice is marked as paid and the payment is registered in the payment journal defined in the configuration of the payment provider. This mode is advised if you issue the final invoice at the order and not after the delivery.
- `quotation_validity_days` **(integer)** — Default Quotation Validity
  > Days between quotation proposal and expiration. 0 days means automatic expiration is disabled
- `portal_confirmation_sign` **(boolean)** — Online Signature
- `portal_confirmation_pay` **(boolean)** — Online Payment
- `prepayment_percent` **(float)** — Prepayment percentage
  > The percentage of the amount needed to be paid to confirm quotations.
- `module_product_email_template` **(boolean)** — Specific Email
- `module_sale_amazon` **(boolean)** — Amazon Sync
- `module_sale_commission` **(boolean)** — Commissions
- `module_sale_gelato` **(boolean)** — Gelato
- `module_sale_loyalty` **(boolean)** — Coupons & Loyalty
- `module_sale_margin` **(boolean)** — Margins
- `module_sale_pdf_quote_builder` **(boolean)** — PDF Quote builder
- `module_sale_product_matrix` **(boolean)** — Sales Grid Entry
- `module_sale_shopee` **(boolean)** — Shopee Sync
- `expense_extract_show_ocr_option_selection` **(selection)** — Expense processing option
  > Opções: `no_send` (Do not digitize), `manual_send` (Digitize on demand only), `auto_send` (Digitize automatically)
- `manufacturing_period` **(selection)** — Manufacturing Period
  > Default value for the time ranges in Master Production Schedule report.
  > Opções: `year` (Yearly), `month` (Monthly), `week` (Weekly), `day` (Daily)
- `manufacturing_period_to_display_year` **(integer)** — Number of Yearly Manufacturing Period Columns
- `manufacturing_period_to_display_month` **(integer)** — Number of Monthly Manufacturing Period Columns
- `manufacturing_period_to_display_week` **(integer)** — Number of Weekly Manufacturing Period Columns
- `manufacturing_period_to_display_day` **(integer)** — Number of Daily Manufacturing Period Columns
- `group_sale_order_template` **(boolean)** — Quotation Templates
- `security_lead` **(float)** — Security Lead Time
  > Margin of error for dates promised to customers. Products will be scheduled for procurement and delivery that many days earlier than the actual promised date, to cope with unexpected delays in the supply chain.
- `use_security_lead` **(boolean)** — Security Lead Time for Sales
  > Margin of error for dates promised to customers. Products will be scheduled for delivery that many days earlier than the actual promised date, to cope with unexpected delays in the supply chain.
- `reminder_user_delay` **(integer)** — Days to Remind User
  > Numbers of days after the end of the week/month after which an automatic email reminder will be sent to timesheet users that still have timesheets to encode (according to their working hours).
- `reminder_delay` **(integer)** — Days to Remind Approver
  > Number of days after the end of the week/month after which an automatic email reminder will be sent to timesheet managers that still have timesheets to validate.
- `timesheet_min_duration` **(integer)** — Minimal Duration
- `timesheet_rounding` **(integer)** — Round up
- `website_slide_google_app_key` **(char)** — Google Doc Key
- `module_website_sale_slides` **(boolean)** — Sell on eCommerce
- `module_website_slides_forum` **(boolean)** — Forum
- `module_website_slides_survey` **(boolean)** — Certifications
- `module_mass_mailing_slides` **(boolean)** — Mailing
- `extract_bank_statement_digitalization_mode` **(selection)** — Bank Statements
  > Opções: `no_send` (Do not digitize), `auto_send` (Digitize automatically)
- `extract_in_invoice_digitalization_mode` **(selection)** — Vendor Bills
  > Opções: `no_send` (Do not digitize), `manual_send` (Digitize on demand only), `auto_send` (Digitize automatically)
- `extract_out_invoice_digitalization_mode` **(selection)** — Customer Invoices
  > Opções: `no_send` (Do not digitize), `manual_send` (Digitize on demand only), `auto_send` (Digitize automatically)
- `extract_single_line_per_tax` **(boolean)** — Single Invoice Line Per Tax
- `l10n_br_avatax_portal_email` **(char)** — Avatax Portal Email
- `l10n_br_avatax_api_identifier` **(char)** — Avalara Brazil API ID
- `l10n_br_avatax_api_key` **(char)** — Avalara Brazil API Key
- `l10n_br_icms_rate` **(float)** — Simplified Regime ICMS Rate
  > This only applies if you are a simplified tax regime company.
- `group_commission_forecast` **(boolean)** — Achievement Forecast
- `group_show_uom_price` **(boolean)** — Base Unit Price
- `group_product_price_comparison` **(boolean)** — Comparison Price
  > Add a strikethrough price to your /shop and product pages for comparison purposes.It will not be displayed if pricelists apply.
- `group_gmc_feed` **(boolean)** — Google Merchant Center
- `module_website_sale_autocomplete` **(boolean)** — Address Autocomplete
- `module_website_sale_collect` **(boolean)** — Click & Collect
- `add_to_cart_action` **(selection)** — Add To Cart Action
  > Opções: `stay` (Stay on Product Page), `go_to_cart` (Go to cart)
- `cart_abandoned_delay` **(float)** — Abandoned Delay
- `send_abandoned_cart_email` **(boolean)** — Abandoned Email
- `website_sale_prevent_zero_price_sale` **(boolean)** — Prevent Sale of Zero Priced Product
- `website_sale_contact_us_button_url` **(char)** — Button Url
- `show_line_subtotals_tax_selection` **(selection)** — Line Subtotals Tax Display
  > Opções: `tax_excluded` (Tax Excluded), `tax_included` (Tax Included)
- `ecommerce_access` **(selection)** — Ecommerce Access
  > Opções: `everyone` (All users), `logged_in` (Logged in users)
- `is_newsletter_enabled` **(boolean)** — Is Newsletter Enabled
- `default_allow_out_of_stock_order` **(boolean)** — Continue selling when out-of-stock
- `default_available_threshold` **(float)** — Show Threshold
- `default_show_availability` **(boolean)** — Show availability Qty
- `l10n_br_is_icbs` **(boolean)** — Enable ICBS
  > Brazil: enable the fiscal reform.
- `l10n_br_is_cbs_ibs_taxpayer` **(boolean)** — CBS/IBS Taxpayer
  > Brazil: Indicates that this entity is subject to CBS/IBS taxation. Used for exempt operations or special regimes.
- `l10n_br_is_cbs_ibs_normal` **(boolean)** — CBS/IBS Normal
  > Brazil: Indicates whether the contact or company under the simplified regime is classified as Normal or Mixed taxation. When enabled, it means the entity follows the Normal regime; when disabled, it indicates the Mixed regime.
- `l10n_br_cbs_credit` **(float)** — CBS Presumed Credit (%)
  > Brazil: Percentage of presumed CBS credit for entities under Simples Nacional "misto" regime.
- `l10n_br_ibs_credit` **(float)** — IBS Presumed Credit (%)
  > Brazil: Percentage of presumed IBS credit for entities under Simples Nacional "misto" regime.
- `invoice_policy` **(boolean)** — Invoice Policy
  > Timesheets taken when invoicing time spent
- `timesheet_show_rates` **(boolean)** — Billing Rate Indicators
  > Show the billing indicators on My Timesheets view
- `timesheet_show_leaderboard` **(boolean)** — Billing Rate Leaderboard
  > Show the leaderboard on My Timesheets view
- `invoiced_timesheet` **(selection)** — Timesheets Invoicing
  > With the 'all recorded timesheets' option, all timesheets will be invoiced without distinction, even if they haven't been validated. Additionally, all timesheets will be accessible in your customers' portal.  When you choose the 'validated timesheets only' option, only the validated timesheets will be invoiced and appear in your customers' portal.
  > Opções: `all` (All recorded timesheets), `approved` (Validated timesheets only)

## Relacionamentos

- `external_report_layout_id` **(many2one)** — Document Template 🔒 readonly → `ir.ui.view`
- `geoloc_provider_id` **(many2one)** — API → `base.geo_provider`
- `alias_domain_id` **(many2one)** — Alias Domain → `mail.alias.domain`
  > If you have setup a catch-all email domain redirected to the Odoo server, enter the domain name here.
- `auth_signup_template_user_id` **(many2one)** — Template user for new users created through signup → `res.users`
- `digest_id` **(many2one)** — Digest Email → `digest.digest`
- `active_provider_id` **(many2one)** — Active Provider 🔒 readonly → `payment.provider`
- `signing_certificate_id` **(many2one)** — Signing certificate → `certificate.certificate`
- `currency_exchange_journal_id` **(many2one)** — Currency Exchange Journal → `account.journal`
  > The accounting journal where automatic exchange differences will be registered
- `income_currency_exchange_account_id` **(many2one)** — Gain Exchange Rate Account → `account.account`
- `expense_currency_exchange_account_id` **(many2one)** — Loss Exchange Rate Account → `account.account`
- `sale_tax_id` **(many2one)** — Default Sale Tax → `account.tax`
- `purchase_tax_id` **(many2one)** — Default Purchase Tax → `account.tax`
- `account_journal_suspense_account_id` **(many2one)** — Bank Suspense → `account.account`
  > Bank Transactions are posted immediately after import or synchronization. Their counterparty is the bank suspense account. Reconciliation replaces the latter by the definitive account(s).
- `transfer_account_id` **(many2one)** — Internal Transfer → `account.account`
  > Intermediary account used when moving from a liquidity account to another.
- `tax_cash_basis_journal_id` **(many2one)** — Tax Cash Basis Journal → `account.journal`
- `account_cash_basis_base_account_id` **(many2one)** — Base Tax Received Account → `account.account`
  > Account that will be set on lines created in cash basis journal entry and used to keep track of the tax base amount.
- `account_fiscal_country_id` **(many2one)** — Fiscal Country Code → `res.country`
  > The country to use the tax reports from for this company
- `incoterm_id` **(many2one)** — Default incoterm → `account.incoterms`
  > International Commercial Terms are a series of predefined commercial terms used in international transactions.
- `account_journal_early_pay_discount_loss_account_id` **(many2one)** — Early Discount Loss → `account.account`
  > Account for the difference amount after the expense discount has been granted
- `account_journal_early_pay_discount_gain_account_id` **(many2one)** — Early Discount Gain → `account.account`
  > Account for the difference amount after the income discount has been granted
- `account_discount_income_allocation_id` **(many2one)** — Vendor Bills Discounts Account → `account.account`
- `account_discount_expense_allocation_id` **(many2one)** — Customer Invoices Discounts Account → `account.account`
- `income_account_id` **(many2one)** — Income Account → `account.account`
  > This account will be used when validating a customer invoice.
- `expense_account_id` **(many2one)** — Expense Account → `account.account`
  > The expense is accounted for when a vendor bill is validated, except in anglo-saxon accounting with perpetual inventory valuation in which case the expense (Cost of Goods Sold account) is recognized at the customer invoice validation.
- `predictive_lead_scoring_fields` **(many2many)** — Lead Scoring Frequency Fields → `crm.lead.scoring.frequency.field`
- `resource_calendar_id` **(many2one)** — Company Working Hours → `resource.calendar`
- `mass_mailing_mail_server_id` **(many2one)** — Mail Server → `ir.mail_server`
- `website_id` **(many2one)** — website → `website`
- `website_company_id` **(many2one)** — Website Company → `res.company`
- `language_ids` **(many2many)** — Languages → `res.lang`
- `website_default_lang_id` **(many2one)** — Default language → `res.lang`
- `send_request_wa_template_id` **(many2one)** — Request template → `whatsapp.template`
  > Choose an approved WhatsApp template to send signature requests
- `request_completion_wa_template_id` **(many2one)** — Completed template → `whatsapp.template`
  > Choose an approved WhatsApp template to send the signature request completion
- `request_refusal_wa_template_id` **(many2one)** — Refusal template → `whatsapp.template`
  > Choose an approved WhatsApp template to send the signature request refusal
- `signing_user` **(many2one)** — Signature used to sign all the invoice → `res.users`
  > Select a user here to override every signature on invoice by this user's signature
- `deferred_expense_journal_id` **(many2one)** — Deferred Expense Journal → `account.journal`
  > Journal used for deferred entries
- `deferred_expense_account_id` **(many2one)** — Deferred Expense Account → `account.account`
  > Account used for deferred expenses
- `deferred_revenue_journal_id` **(many2one)** — Deferred Revenue Journal → `account.journal`
  > Journal used for deferred entries
- `deferred_revenue_account_id` **(many2one)** — Deferred Revenue Account → `account.account`
  > Account used for deferred revenues
- `documents_employee_folder_id` **(many2one)** — Employees Folder → `documents.document`
- `documents_hr_contracts_tags` **(many2many)** — Contracts → `documents.tag`
- `product_folder_id` **(many2one)** — product default folder → `documents.document`
- `product_tag_ids` **(many2many)** — Product Tags → `documents.tag`
- `documents_project_folder_id` **(many2one)** — Project Folder → `documents.document`
- `hr_expense_alias_domain_id` **(many2one)** — Hr Expense Alias Domain → `mail.alias.domain`
- `expense_journal_id` **(many2one)** — Default Expense Journal → `account.journal`
  > The company's default journal used when an employee expense is created.
- `company_expense_allowed_payment_method_line_ids` **(many2many)** — Payment methods available for expenses paid by company → `account.payment.method.line`
- `company_currency_id` **(many2one)** — Company Currency 🔒 readonly → `res.currency`
- `barcode_nomenclature_id` **(many2one)** — Nomenclature → `barcode.nomenclature`
- `stock_sms_confirmation_template_id` **(many2one)** — SMS Template → `sms.template`
  > SMS sent to the customer once the order is delivered.
- `account_tax_return_journal_id` **(many2one)** — Journal → `account.journal`
- `approvals_folder_id` **(many2one)** — Approvals default folder → `documents.document`
- `approvals_tag_ids` **(many2many)** — Approvals Tags → `documents.tag`
- `assessment_note_ids` **(one2many)** — Evaluation Scale → `hr.appraisal.note`
- `project_time_mode_id` **(many2one)** — Project Time Unit → `uom.uom`
  > This will set the unit of measure used in projects and tasks. If you use the timesheet linked to projects, don't forget to setup the right unit of measure in your employees.
- `invoice_mail_template_id` **(many2one)** — Email Template → `mail.template`
  > Email sent to the customer once the invoice is available.
- `downpayment_account_id` **(many2one)** — Downpayment Account → `account.account`
  > This account will be used on Downpayment invoices.
- `stock_confirmation_wa_template_id` **(many2one)** — WhatsApp Template → `whatsapp.template`
  > Send WhatsApp to the customer once the order is delivered.
- `account_folder_id` **(many2one)** — account default folder → `documents.document`
- `company_so_template_id` **(many2one)** — Default Template → `sale.order.template`
- `stock_journal` **(many2one)** — Stock Journal → `account.journal`
- `stock_valuation_account_id` **(many2one)** — Stock Valuation Account → `account.account`
- `l10n_br_cnae_code_id` **(many2one)** — CNAE Code → `l10n_br.cnae.code`
  > Main CNAE code registered with the government.
- `account_production_wip_account_id` **(many2one)** — WIP Account → `account.account`
- `account_production_wip_overhead_account_id` **(many2one)** — WIP Overhead Account → `account.account`
- `cart_recovery_mail_template` **(many2one)** — Cart Recovery Email → `mail.template`
- `salesperson_id` **(many2one)** — Salesperson → `res.users`
- `salesteam_id` **(many2one)** — Sales Team → `crm.team`
- `confirmation_email_template_id` **(many2one)** — Confirmation Email Template → `mail.template`
- `newsletter_id` **(many2one)** — Newsletter List → `mailing.list`
- `website_warehouse_id` **(many2one)** — Warehouse → `stock.warehouse`
- `wa_sale_template_id` **(many2one)** — Wa Sale Template → `whatsapp.template`

## Campos Calculados (readonly)

- `is_root_company` **(boolean)** — Is Root Company 🔒 readonly
- `company_count` **(integer)** — Number of Companies 🔒 readonly
- `active_user_count` **(integer)** — Number of Active Users 🔒 readonly
- `language_count` **(integer)** — Number of Languages 🔒 readonly
- `company_name` **(char)** — Company Name 🔒 readonly
- `company_informations` **(text)** — Company Informations 🔒 readonly
- `company_country_code` **(char)** — Company Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `company_country_group_codes` **(json)** — Country Group Codes 🔒 readonly
- `geoloc_provider_techname` **(char)** — Technical Name 🔒 readonly
- `fail_counter` **(integer)** — Fail Mail 🔒 readonly
- `partner_autocomplete_insufficient_credit` **(boolean)** — Insufficient credit 🔒 readonly
- `snailmail_cover_readonly` **(boolean)** — Snailmail Cover Readonly 🔒 readonly
- `has_enabled_provider` **(boolean)** — Has Enabled Provider 🔒 readonly
- `onboarding_payment_module` **(selection)** — Onboarding Payment Module 🔒 readonly
  > Opções: `mercado_pago` (Mercado Pago), `razorpay` (Razorpay), `stripe` (Stripe)
- `sign_preview_ready` **(boolean)** — Display sign preview button 🔒 readonly
- `has_accounting_entries` **(boolean)** — Has Accounting Entries 🔒 readonly
- `has_chart_of_accounts` **(boolean)** — Company has a chart of accounts 🔒 readonly
- `preview_ready` **(boolean)** — Display preview button 🔒 readonly
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `display_account_storno` **(boolean)** — Display Account Storno 🔒 readonly
- `is_account_peppol_eligible` **(boolean)** — PEPPOL eligible 🔒 readonly
- `predictive_lead_scoring_field_labels` **(char)** — Predictive Lead Scoring Field Labels 🔒 readonly
- `website_language_count` **(integer)** — Number of languages 🔒 readonly
- `module_sign` **(boolean)** — Sign 🔒 readonly
- `attendance_kiosk_url` **(char)** — Attendance Kiosk Url 🔒 readonly
- `stock_barcode_demo_active` **(boolean)** — Demo Data Active 🔒 readonly
- `show_barcode_nomenclature` **(boolean)** — Show Barcode Nomenclature 🔒 readonly
- `is_encode_uom_days` **(boolean)** — Is Encode Uom Days 🔒 readonly
- `l10n_br_avatax_show_overwrite_warning` **(boolean)** — L10N Br Avatax Show Overwrite Warning 🔒 readonly
  > Technical field used to determine whether or not the user is about to overwrite his current API credentialswith new ones, since the old credentials won't be recoverable we warn.
- `l10n_br_tax_regime` **(selection)** — Tax Regime 🔒 readonly
  > Brazil: Contact FederalTax Regime
  > Opções: `realProfit` (realProfit), `estimatedProfit` (estimatedProfit), `simplified` (simplified), `simplifiedHybrid` (simplifiedHybrid), `simplifiedOverGrossthreshold` (simplifiedOverGrossthreshold), `simplifiedEntrepreneur` (simplifiedEntrepreneur), `notApplicable` (notApplicable), `individual` (individual), `variable` (variable)
- `l10n_br_avatax_show_existing_account_warning` **(boolean)** — L10N Br Avatax Show Existing Account Warning 🔒 readonly
