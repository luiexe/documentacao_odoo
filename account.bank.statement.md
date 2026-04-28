# Bank Statement — `account.bank.statement`

**Ordenação padrão:** `first_line_index desc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Reference
- `reference` **(char)** — External Reference
- `date` **(date)** — Date
- `first_line_index` **(char)** — First Line Index 🔒 readonly
- `balance_start` **(monetary)** — Starting Balance
- `balance_end` **(monetary)** — Computed Balance 🔒 readonly
- `balance_end_real` **(monetary)** — Ending Balance
- `is_complete` **(boolean)** — Is Complete 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `extract_state` **(selection)** — Extract state
  > Opções: `no_extract_requested` (No extract requested), `not_enough_credit` (Not enough credits), `error_status` (An error occurred), `waiting_extraction` (Waiting extraction), `extract_not_ready` (waiting extraction, but it is not ready), `waiting_validation` (Waiting validation), `to_validate` (To validate), `done` (Completed flow)
- `extract_status` **(char)** — Extract status
- `extract_document_uuid` **(char)** — ID of the request to IAP-OCR 🔒 readonly
- `is_in_extractable_state` **(boolean)** — Is In Extractable State 🔒 readonly
- `extract_state_processed` **(boolean)** — Extract State Processed 🔒 readonly
- `extracted_words` **(json)** — Extracted Words
- `extracted_numbers` **(json)** — Extracted Numbers
- `extracted_dates` **(json)** — Extracted Dates

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
  > Company related to this journal
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `journal_id` **(many2one)** — Journal 🔒 readonly → `account.journal`
- `line_ids` **(one2many)** — Statement lines → `account.bank.statement.line`
- `attachment_ids` **(many2many)** — Attachments → `ir.attachment`
- `message_main_attachment_id` **(many2one)** — Main Attachment → `ir.attachment`
- `extract_attachment_id` **(many2one)** — Extract Attachment 🔒 readonly → `ir.attachment`

## Campos Calculados (readonly)

- `is_valid` **(boolean)** — Is Valid 🔒 readonly
- `journal_has_invalid_statements` **(boolean)** — Has Invalid Statements 🔒 readonly
- `problem_description` **(text)** — Problem Description 🔒 readonly
- `extract_error_message` **(text)** — Error message 🔒 readonly
- `extract_can_show_send_button` **(boolean)** — Can show the ocr send button 🔒 readonly
