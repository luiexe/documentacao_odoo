# This allows a user to inform the government a range of sequence numbers won't be used. — `l10n_br_edi.cancel.range`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `journal_id` **(many2one)** — Journal ⚠️ obrigatório 🔒 readonly → `account.journal`
  > The journal for which to invalidate the range.
- `document_type_id` **(many2one)** — Document Type ⚠️ obrigatório → `l10n_latam.document.type`
  > The document type for which to invalidate the range.
- `start_number` **(integer)** — Start number ⚠️ obrigatório
  > The first number that should be invalidated.
- `end_number` **(integer)** — End number ⚠️ obrigatório
  > The last number that should be invalidated.
- `reason` **(char)** — Reason ⚠️ obrigatório
  > The reason for invalidating this range.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
