# Preview template — `whatsapp.preview`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `wa_template_id` **(many2one)** — Templates → `whatsapp.template`

## Campos Calculados (readonly)

- `preview_whatsapp` **(html)** — Message Preview 🔒 readonly
