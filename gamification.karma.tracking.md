# Track Karma Changes — `gamification.karma.tracking`

**Ordenação padrão:** `tracking_date desc, id desc`

---

## Campos Obrigatórios

- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`
- `new_value` **(integer)** — New Karma Value ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `old_value` **(integer)** — Old Karma Value 🔒 readonly
- `gain` **(integer)** — Gain
- `consolidated` **(boolean)** — Consolidated
- `tracking_date` **(datetime)** — Tracking Date 🔒 readonly
- `reason` **(text)** — Description
- `origin_ref` **(reference)** — Source
  > Opções: `res.users` (User), `slide.slide` (Course Quiz), `slide.channel` (Course)
- `origin_ref_model_name` **(selection)** — Source Type 🔒 readonly
  > Opções: `res.users` (User), `slide.slide` (Course Quiz), `slide.channel` (Course)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
