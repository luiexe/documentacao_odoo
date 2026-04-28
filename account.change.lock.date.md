# Change Lock Date — `account.change.lock.date`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `exception_applies_to` **(selection)** — Exception applies ⚠️ obrigatório
  > Opções: `me` (for me), `everyone` (for everyone)
- `exception_duration` **(selection)** — Exception Duration ⚠️ obrigatório
  > Opções: `5min` (for 5 minutes), `15min` (for 15 minutes), `1h` (for 1 hour), `24h` (for 24 hours), `forever` (forever)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `fiscalyear_lock_date` **(date)** — Lock Everything
  > Any entry up to and including that date will be postponed to a later time, in accordance with its journal's sequence.
- `tax_lock_date` **(date)** — Lock Tax Return
  > Any entry with taxes up to and including that date will be postponed to a later time, in accordance with its journal's sequence. The tax lock date is automatically set when the tax closing entry is posted.
- `sale_lock_date` **(date)** — Lock Sales
  > Any sales entry prior to and including this date will be postponed to a later date, in accordance with its journal's sequence.
- `purchase_lock_date` **(date)** — Lock Purchases
  > Any purchase entry prior to and including this date will be postponed to a later date, in accordance with its journal's sequence.
- `hard_lock_date` **(date)** — Hard Lock
  > Any entry up to and including that date will be postponed to a later time, in accordance with its journal sequence. This lock date is irreversible and does not allow any exception.
- `exception_reason` **(char)** — Exception Reason
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `min_fiscalyear_lock_date_exception_for_me_id` **(many2one)** — Min Fiscalyear Lock Date Exception For Me 🔒 readonly → `account.lock_exception`
- `min_fiscalyear_lock_date_exception_for_everyone_id` **(many2one)** — Min Fiscalyear Lock Date Exception For Everyone 🔒 readonly → `account.lock_exception`
- `min_tax_lock_date_exception_for_me_id` **(many2one)** — Min Tax Lock Date Exception For Me 🔒 readonly → `account.lock_exception`
- `min_tax_lock_date_exception_for_everyone_id` **(many2one)** — Min Tax Lock Date Exception For Everyone 🔒 readonly → `account.lock_exception`
- `min_sale_lock_date_exception_for_me_id` **(many2one)** — Min Sale Lock Date Exception For Me 🔒 readonly → `account.lock_exception`
- `min_sale_lock_date_exception_for_everyone_id` **(many2one)** — Min Sale Lock Date Exception For Everyone 🔒 readonly → `account.lock_exception`
- `min_purchase_lock_date_exception_for_me_id` **(many2one)** — Min Purchase Lock Date Exception For Me 🔒 readonly → `account.lock_exception`
- `min_purchase_lock_date_exception_for_everyone_id` **(many2one)** — Min Purchase Lock Date Exception For Everyone 🔒 readonly → `account.lock_exception`

## Campos Calculados (readonly)

- `fiscalyear_lock_date_for_me` **(date)** — Lock Everything For Me 🔒 readonly
- `fiscalyear_lock_date_for_everyone` **(date)** — Lock Everything For Everyone 🔒 readonly
- `tax_lock_date_for_me` **(date)** — Lock Tax Return For Me 🔒 readonly
- `tax_lock_date_for_everyone` **(date)** — Lock Tax Return For Everyone 🔒 readonly
- `sale_lock_date_for_me` **(date)** — Lock Sales For Me 🔒 readonly
- `sale_lock_date_for_everyone` **(date)** — Lock Sales For Everyone 🔒 readonly
- `purchase_lock_date_for_me` **(date)** — Lock Purchases For Me 🔒 readonly
- `purchase_lock_date_for_everyone` **(date)** — Lock Purchases For Everyone 🔒 readonly
- `current_hard_lock_date` **(date)** — Current Hard Lock 🔒 readonly
  > Any entry up to and including that date will be postponed to a later time, in accordance with its journal sequence. This lock date is irreversible and does not allow any exception.
- `exception_needed_fields` **(char)** — Exception Needed Fields 🔒 readonly
- `show_draft_entries_warning` **(boolean)** — Show Draft Entries Warning 🔒 readonly
- `show_posted_tax_closing_warning` **(boolean)** — Show Posted Tax Closing Warning 🔒 readonly
