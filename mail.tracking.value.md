# Mail Tracking Value — `mail.tracking.value`

**Ordenação padrão:** `id DESC`

---

## Campos Obrigatórios

- `mail_message_id` **(many2one)** — Message ID ⚠️ obrigatório → `mail.message`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `field_info` **(json)** — Removed field information
- `old_value_integer` **(integer)** — Old Value Integer 🔒 readonly
- `old_value_float` **(float)** — Old Value Float 🔒 readonly
- `old_value_char` **(char)** — Old Value Char 🔒 readonly
- `old_value_text` **(text)** — Old Value Text 🔒 readonly
- `old_value_datetime` **(datetime)** — Old Value DateTime 🔒 readonly
- `new_value_integer` **(integer)** — New Value Integer 🔒 readonly
- `new_value_float` **(float)** — New Value Float 🔒 readonly
- `new_value_char` **(char)** — New Value Char 🔒 readonly
- `new_value_text` **(text)** — New Value Text 🔒 readonly
- `new_value_datetime` **(datetime)** — New Value Datetime 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `field_id` **(many2one)** — Field 🔒 readonly → `ir.model.fields`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
  > Used to display the currency when tracking monetary values
