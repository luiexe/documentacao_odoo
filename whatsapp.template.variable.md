# WhatsApp Template Variable — `whatsapp.template.variable`

**Ordenação padrão:** `line_type desc, name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Placeholder ⚠️ obrigatório
- `wa_template_id` **(many2one)** — Wa Template ⚠️ obrigatório → `whatsapp.template`
- `line_type` **(selection)** — Variable location ⚠️ obrigatório
  > Opções: `button` (Button), `header` (Header), `location` (Location), `body` (Body)
- `field_type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `user_name` (User Name), `user_phone` (User Phone), `free_text` (Free Text), `portal_url` (Portal Link), `field` (Field of Model)
- `demo_value` **(char)** — Sample Value ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `field_name` **(char)** — Field
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `button_id` **(many2one)** — Button → `whatsapp.template.button`

## Campos Calculados (readonly)

- `model` **(char)** — Model Name 🔒 readonly
