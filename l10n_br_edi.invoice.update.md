# Implements both correcting and cancelling an invoice. — `l10n_br_edi.invoice.update`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `move_id` **(many2one)** — Move To Cancel ⚠️ obrigatório → `account.move`
  > The move to be cancelled.
- `mode` **(selection)** — Mode ⚠️ obrigatório 🔒 readonly
  > Technical field to determine whether the move is cancelled or corrected.
  > Opções: `cancel` (Cancel), `correct` (Correct)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `reason` **(char)** — Reason
  > The justification for altering this move.
- `send_email` **(boolean)** — Email
  > When checked an email will be sent informing the customer of the changes and the new EDI documents.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `is_service_invoice` **(boolean)** — Is Service Invoice 🔒 readonly
  > Technical field used to hide the "reason" field.
