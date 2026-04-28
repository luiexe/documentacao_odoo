# Cleaning Rule — `data_cleaning.rule`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `cleaning_model_id` **(many2one)** — Cleaning Model ⚠️ obrigatório → `data_cleaning.model`
- `field_id` **(many2one)** — Field ⚠️ obrigatório → `ir.model.fields`
- `action` **(selection)** — Action ⚠️ obrigatório
  > Opções: `trim` (Trim Spaces), `case` (Set Type Case), `phone` (Format Phone), `html` (Scrap HTML)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `res_model_name` **(char)** — Model Name 🔒 readonly
- `action_trim` **(selection)** — Trim
  > Which spaces are trimmed by the rule. Leading, trailing, and successive spaces are considered superfluous.
  > Opções: `all` (All Spaces), `superfluous` (Superfluous Spaces)
- `action_case` **(selection)** — Case
  > How the type case is set by the rule. 'First Letters to Uppercase' sets every letter to lowercase except the first letter of each word, which is set to uppercase.
  > Opções: `first` (First Letters to Uppercase), `upper` (All Uppercase), `lower` (All Lowercase)
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `res_model_id` **(many2one)** — Model 🔒 readonly → `ir.model`

## Campos Calculados (readonly)

- `name` **(char)** — Field Name 🔒 readonly
- `action_technical` **(char)** — Action Technical 🔒 readonly
- `action_display` **(char)** — Action Display 🔒 readonly
