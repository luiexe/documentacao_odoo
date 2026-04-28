# Send SMS Wizard — `sms.composer`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `composition_mode` **(selection)** — Composition Mode ⚠️ obrigatório
  > Opções: `numbers` (Send to numbers), `comment` (Post on a document), `mass` (Send SMS in batch)
- `body` **(text)** — Message ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `res_model` **(char)** — Document Model Name
- `res_id` **(integer)** — Document ID
- `res_ids` **(char)** — Document IDs
- `mass_keep_log` **(boolean)** — Keep a note on document
- `mass_force_send` **(boolean)** — Send directly
- `use_exclusion_list` **(boolean)** — Use Exclusion List
  > Prevent sending messages to blacklisted contacts. Disable only when absolutely necessary.
- `recipient_single_number_itf` **(char)** — Recipient Number
  > Phone number of the recipient. If changed, it will be recorded on recipient's profile.
- `number_field_name` **(char)** — Number Field
- `numbers` **(char)** — Recipients (Numbers)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `template_id` **(many2one)** — Use Template → `sms.template`

## Campos Calculados (readonly)

- `res_model_description` **(char)** — Document Model Description 🔒 readonly
- `res_ids_count` **(integer)** — Visible records count 🔒 readonly
  > Number of recipients that will receive the SMS if sent in mass mode, without applying the Active Domain value
- `comment_single_recipient` **(boolean)** — Single Mode 🔒 readonly
  > Indicates if the SMS composer targets a single specific recipient
- `recipient_valid_count` **(integer)** — # Valid recipients 🔒 readonly
- `recipient_invalid_count` **(integer)** — # Invalid recipients 🔒 readonly
- `recipient_single_description` **(text)** — Recipients (Partners) 🔒 readonly
- `recipient_single_number` **(char)** — Stored Recipient Number 🔒 readonly
- `recipient_single_valid` **(boolean)** — Is valid 🔒 readonly
- `sanitized_numbers` **(char)** — Sanitized Number 🔒 readonly
