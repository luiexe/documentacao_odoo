# SMS Templates — `sms.template`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `model_id` **(many2one)** — Applies to ⚠️ obrigatório → `ir.model`
  > The type of document this template can be used with
- `body` **(char)** — Body ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `template_fs` **(char)** — Template Filename
  > File from where the template originates. Used to reset broken template.
- `lang` **(char)** — Language
  > Optional translation language (ISO code) to select when sending out an email. If not set, the main partner's language will be used. This should usually be a placeholder expression that provides the appropriate language, e.g. {{ object.partner_id.lang }}.
- `name` **(char)** — Name
- `model` **(char)** — Related Document Model 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `sidebar_action_id` **(many2one)** — Sidebar action 🔒 readonly → `ir.actions.act_window`
  > Sidebar action to make this template available on records of the related document model

## Campos Calculados (readonly)

- `render_model` **(char)** — Rendering Model 🔒 readonly
