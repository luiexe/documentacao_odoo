# Content Quiz Question — `slide.question`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `question` **(char)** — Question Name ⚠️ obrigatório
- `slide_id` **(many2one)** — Content ⚠️ obrigatório → `slide.slide`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `answer_ids` **(one2many)** — Answer → `slide.answer`

## Campos Calculados (readonly)

- `answers_validation_error` **(char)** — Error on Answers 🔒 readonly
