# Add Debit Note wizard — `account.debit.note`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `date` **(date)** — Debit Note Date ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `reason` **(char)** — Reason
- `copy_lines` **(boolean)** — Copy Lines
  > In case you need to do corrections for every line, it can be in handy to copy them.  We won't copy them for debit notes from credit notes. 
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `move_ids` **(many2many)** — Move → `account.move`
- `journal_id` **(many2one)** — Use Specific Journal → `account.journal`
  > If empty, uses the journal of the journal entry to be debited.

## Campos Calculados (readonly)

- `move_type` **(char)** — Move Type 🔒 readonly
- `journal_type` **(char)** — Journal Type 🔒 readonly
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
