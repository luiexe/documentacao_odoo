# Gamification generic goal for challenge — `gamification.challenge.line`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `challenge_id` **(many2one)** — Challenge ⚠️ obrigatório → `gamification.challenge`
- `definition_id` **(many2one)** — Goal Definition ⚠️ obrigatório → `gamification.goal.definition`
- `target_goal` **(float)** — Target Value to Reach ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `name` **(char)** — Name
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `condition` **(selection)** — Condition 🔒 readonly
  > A goal is considered as completed when the current value is compared to the value to reach
  > Opções: `higher` (The higher the better), `lower` (The lower the better)
- `definition_suffix` **(char)** — Unit 🔒 readonly
  > The unit of the target and current values
- `definition_monetary` **(boolean)** — Monetary 🔒 readonly
  > The target and current value are defined in the company currency.
- `definition_full_suffix` **(char)** — Suffix 🔒 readonly
  > The currency and suffix field
