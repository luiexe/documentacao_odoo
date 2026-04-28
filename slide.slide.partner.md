# Slide / Partner decorated m2m — `slide.slide.partner`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `slide_id` **(many2one)** — Content ⚠️ obrigatório → `slide.slide`
- `partner_id` **(many2one)** — Partner ⚠️ obrigatório → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `vote` **(integer)** — Vote
- `completed` **(boolean)** — Completed
- `quiz_attempts_count` **(integer)** — Quiz attempts count
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `survey_scoring_success` **(boolean)** — Certification Succeeded 🔒 readonly

## Relacionamentos

- `channel_id` **(many2one)** — Channel 🔒 readonly → `slide.channel`
- `user_input_ids` **(one2many)** — Certification attempts → `survey.user_input`

## Campos Calculados (readonly)

- `slide_category` **(selection)** — Category 🔒 readonly
  > Opções: `infographic` (Image), `article` (Article), `document` (Document), `video` (Video), `quiz` (Quiz), `certification` (Certification)
