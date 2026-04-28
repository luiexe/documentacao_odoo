# Send WhatsApp Wizard — `whatsapp.composer`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `res_ids` **(char)** — Document IDs ⚠️ obrigatório
- `res_model` **(char)** — Document Model Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `batch_mode` **(boolean)** — Is Multiple Records
- `phone` **(char)** — Phone
- `header_text_1` **(char)** — Header Free Text
- `free_text_1` **(char)** — Free Text 1
- `free_text_2` **(char)** — Free Text 2
- `free_text_3` **(char)** — Free Text 3
- `free_text_4` **(char)** — Free Text 4
- `free_text_5` **(char)** — Free Text 5
- `free_text_6` **(char)** — Free Text 6
- `free_text_7` **(char)** — Free Text 7
- `free_text_8` **(char)** — Free Text 8
- `free_text_9` **(char)** — Free Text 9
- `free_text_10` **(char)** — Free Text 10
- `button_dynamic_url_1` **(char)** — Button Url 1
- `button_dynamic_url_2` **(char)** — Button Url 2
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `attachment_id` **(many2one)** — Attachment → `ir.attachment`
- `wa_template_id` **(many2one)** — Template → `whatsapp.template`

## Campos Calculados (readonly)

- `invalid_phone_number_count` **(integer)** — Invalid Phone Number Count 🔒 readonly
- `preview_whatsapp` **(html)** — Message Preview 🔒 readonly
- `number_of_free_text` **(integer)** — Number of free text 🔒 readonly
- `number_of_free_text_button` **(integer)** — Number of free text Buttons 🔒 readonly
- `is_header_free_text` **(boolean)** — Is Header Free Text 🔒 readonly
- `is_button_dynamic` **(boolean)** — Is Button Dynamic 🔒 readonly
- `is_demo_account` **(boolean)** — Is Demo Account 🔒 readonly
