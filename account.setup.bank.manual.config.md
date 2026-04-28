# Bank setup manual config — `account.setup.bank.manual.config`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `res_partner_bank_id` **(many2one)** — Res Partner Bank ⚠️ obrigatório → `res.partner.bank`
- `new_journal_name` **(char)** — New Journal Name ⚠️ obrigatório
  > Will be used to name the Journal related to this bank account
- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `acc_number` **(char)** — Account Number ⚠️ obrigatório
- `partner_id` **(many2one)** — Account Holder ⚠️ obrigatório → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `bank_bic` **(char)** — Bic
  > Sometimes called BIC or Swift.
- `num_journals_without_account_bank` **(integer)** — Num Journals Without Account Bank
- `num_journals_without_account_credit` **(integer)** — Num Journals Without Account Credit
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `active` **(boolean)** — Active
- `clearing_number` **(char)** — Clearing Number
- `acc_holder_name` **(char)** — Account Holder Name
  > Account holder name, in case it is different than the name of the Account Holder
- `allow_out_payment` **(boolean)** — Send Money
  > Sending fake invoices with a fraudulent account number is a common phishing practice. To protect yourself, always verify new bank account numbers, preferably by calling the vendor, as phishing usually happens when their emails are compromised. Once verified, you can activate the ability to send money.
- `bank_name` **(char)** — Name
- `sequence` **(integer)** — Sequence
- `note` **(text)** — Notes
- `bank_street` **(char)** — Street
- `bank_street2` **(char)** — Street2
- `bank_zip` **(char)** — Zip
- `bank_city` **(char)** — City
- `bank_email` **(char)** — Email
- `bank_phone` **(char)** — Phone
- `include_reference` **(boolean)** — Include Reference
  > Include the reference in the QR code.
- `proxy_type` **(selection)** — Proxy Type
  > Opções: `none` (None), `email` (Email Address), `mobile` (Mobile Number), `br_cpf_cnpj` (CPF/CNPJ (BR)), `br_random` (Random Key (BR))
- `proxy_value` **(char)** — Proxy Value

## Relacionamentos

- `linked_journal_id` **(many2one)** — Journal → `account.journal`
- `bank_id` **(many2one)** — Bank → `res.bank`
- `currency_id` **(many2one)** — Currency → `res.currency`
- `journal_id` **(one2many)** — Account Journal 🔒 readonly → `account.journal`
  > The accounting journal corresponding to this bank account.
- `related_moves` **(one2many)** — Related Moves → `account.move`
- `duplicate_bank_partner_ids` **(many2many)** — Duplicate Bank Partner 🔒 readonly → `res.partner`
- `bank_state` **(many2one)** — Fed. State → `res.country.state`
- `bank_country` **(many2one)** — Country → `res.country`
- `employee_id` **(many2many)** — Employee 🔒 readonly → `hr.employee`

## Campos Calculados (readonly)

- `acc_type` **(selection)** — Type 🔒 readonly
  > Bank account type: Normal or IBAN. Inferred from the bank account number.
  > Opções: `bank` (Normal)
- `sanitized_acc_number` **(char)** — Sanitized Account Number 🔒 readonly
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `color` **(integer)** — Color 🔒 readonly
- `has_iban_warning` **(boolean)** — Has Iban Warning 🔒 readonly
  > Technical field used to display a warning if the IBAN country is different than the holder country.
- `partner_country_name` **(char)** — Country Name 🔒 readonly
- `has_money_transfer_warning` **(boolean)** — Has Money Transfer Warning 🔒 readonly
  > Technical field used to display a warning if the account is a transfer service account.
- `money_transfer_service` **(char)** — Money Transfer Service 🔒 readonly
- `partner_supplier_rank` **(integer)** — Supplier Rank 🔒 readonly
- `partner_customer_rank` **(integer)** — Customer Rank 🔒 readonly
- `user_has_group_validate_bank_account` **(boolean)** — User Has Group Validate Bank Account 🔒 readonly
- `lock_trust_fields` **(boolean)** — Lock Trust Fields 🔒 readonly
- `employee_salary_amount` **(float)** — Salary Allocation 🔒 readonly
- `employee_salary_amount_is_percentage` **(boolean)** — Employee Salary Amount Is Percentage 🔒 readonly
- `currency_symbol` **(char)** — Symbol 🔒 readonly
  > Currency sign, to be used when printing amounts.
- `employee_has_multiple_bank_accounts` **(boolean)** — Has Multiple Bank Accounts 🔒 readonly
- `display_qr_setting` **(boolean)** — Display Qr Setting 🔒 readonly
- `country_proxy_keys` **(char)** — Country Proxy Keys 🔒 readonly
