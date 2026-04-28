# Base class to extract data from documents with OCRed words saved — `extract.mixin.with.words`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
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

- `message_main_attachment_id` **(many2one)** — Main Attachment → `ir.attachment`
- `extract_attachment_id` **(many2one)** — Extract Attachment 🔒 readonly → `ir.attachment`

## Campos Calculados (readonly)

- `extract_error_message` **(text)** — Error message 🔒 readonly
- `extract_can_show_send_button` **(boolean)** — Can show the ocr send button 🔒 readonly
