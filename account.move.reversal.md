# Account Move Reversal — `account.move.reversal`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `journal_id` **(many2one)** — Journal ⚠️ obrigatório → `account.journal`
  > If empty, uses the journal of the journal entry to be reversed.
- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date` **(date)** — Reversal date
- `reason` **(char)** — Reason displayed on Credit Note
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `l10n_latam_document_number` **(char)** — Document Number

## Relacionamentos

- `move_ids` **(many2many)** — Move → `account.move`
- `new_move_ids` **(many2many)** — New Move → `account.move`
- `available_journal_ids` **(many2many)** — Available Journal 🔒 readonly → `account.journal`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `l10n_latam_document_type_id` **(many2one)** — Document Type → `l10n_latam.document.type`
- `l10n_latam_available_document_type_ids` **(many2many)** — L10N Latam Available Document Type 🔒 readonly → `l10n_latam.document.type`

## Campos Calculados (readonly)

- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `residual` **(monetary)** — Residual 🔒 readonly
- `move_type` **(char)** — Move Type 🔒 readonly
- `l10n_latam_use_documents` **(boolean)** — L10N Latam Use Documents 🔒 readonly
- `l10n_latam_manual_document_number` **(boolean)** — Manual Number 🔒 readonly
