# Signature Item Type — `sign.item.type`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Field Name ⚠️ obrigatório
- `item_type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `signature` (Signature), `initial` (Initial), `text` (Text), `textarea` (Multiline Text), `checkbox` (Checkbox), `radio` (Radio), `selection` (Selection), `strikethrough` (Strikethrough), `stamp` (Stamp)
- `tip` **(char)** — Tip ⚠️ obrigatório
  > Hint displayed in the signing hint
- `field_size` **(selection)** — Field Size ⚠️ obrigatório
  > Opções: `short_text` (Short Text), `regular_text` (Regular Text), `long_text` (Long Text)
- `default_width` **(float)** — Default Width ⚠️ obrigatório 🔒 readonly
- `default_height` **(float)** — Default Height ⚠️ obrigatório 🔒 readonly

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `icon` **(char)** — Icon
- `placeholder` **(char)** — Placeholder
- `auto_field` **(char)** — Linked field
  > Technical name of the field on the partner model to auto-complete this signature field at the time of signature.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `model_id` **(many2one)** — Linked to → `ir.model`

## Campos Calculados (readonly)

- `model_name` **(char)** — Model 🔒 readonly
