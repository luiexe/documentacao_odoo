# Opening Balance of Financial Year — `account.financial.year.op`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `opening_date` **(date)** — Opening Date ⚠️ obrigatório
  > Date from which the accounting is managed in Odoo. It is the date of the opening entry.
- `fiscalyear_last_day` **(integer)** — Fiscalyear Last Day ⚠️ obrigatório
  > The last day of the month will be used if the chosen day doesn't exist.
- `fiscalyear_last_month` **(selection)** — Fiscalyear Last Month ⚠️ obrigatório
  > The last day of the month will be used if the chosen day doesn't exist.
  > Opções: `1` (January), `2` (February), `3` (March), `4` (April), `5` (May), `6` (June), `7` (July), `8` (August), `9` (September), `10` (October), `11` (November), `12` (December)
- `account_return_periodicity` **(selection)** — Periodicity in month ⚠️ obrigatório
  > Periodicity
  > Opções: `monthly` (Monthly), `2_months` (Every 2 months), `trimester` (Quarterly), `4_months` (Every 4 months), `semester` (Semi-annually), `year` (Annually), `fiscalyear` (Fiscal Year)
- `account_return_reminder_day` **(integer)** — Reminder ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `account_tax_return_journal_id` **(many2one)** — Journal → `account.journal`

## Campos Calculados (readonly)

- `opening_move_posted` **(boolean)** — Opening Move Posted 🔒 readonly
- `vat_label` **(char)** — Vat Label 🔒 readonly
  > Use this field if you want to change vat label.
