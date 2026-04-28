# WhatsApp Template Button — `whatsapp.template.button`

**Ordenação padrão:** `sequence,id`

---

## Campos Obrigatórios

- `wa_template_id` **(many2one)** — Wa Template ⚠️ obrigatório → `whatsapp.template`
- `button_type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `url` (Visit Website), `phone_number` (Call Number), `quick_reply` (Quick Reply)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `name` **(char)** — Button Text
- `url_type` **(selection)** — Url Type
  > Opções: `static` (Static), `dynamic` (Dynamic), `tracked` (Tracked)
- `website_url` **(char)** — Website URL
- `call_number` **(char)** — Call Number
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `variable_ids` **(one2many)** — Variable 🔒 readonly → `whatsapp.template.variable`

## Campos Calculados (readonly)

- `has_invalid_number` **(boolean)** — Has Invalid Number 🔒 readonly
