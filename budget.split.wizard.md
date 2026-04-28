# Budget Split Wizard — `budget.split.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `date_from` **(date)** — Start Date ⚠️ obrigatório
- `date_to` **(date)** — End Date ⚠️ obrigatório
- `period` **(selection)** — Period ⚠️ obrigatório
  > Opções: `month` (Month), `quarter` (Quarter), `year` (Year)
- `analytical_plan_ids` **(many2many)** — Analytic Plans ⚠️ obrigatório → `account.analytic.plan`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
