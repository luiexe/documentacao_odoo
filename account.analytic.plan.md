# Analytic Plans — `account.analytic.plan`

**Ordenação padrão:** `sequence asc, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(text)** — Description
- `parent_path` **(char)** — Parent Path
- `complete_name` **(char)** — Complete Name 🔒 readonly
- `color` **(integer)** — Color
- `sequence` **(integer)** — Sequence
- `default_applicability` **(selection)** — Default Applicability
  > Opções: `optional` (Optional), `mandatory` (Mandatory), `unavailable` (Unavailable)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `parent_id` **(many2one)** — Parent → `account.analytic.plan`
- `root_id` **(many2one)** — Root 🔒 readonly → `account.analytic.plan`
- `children_ids` **(one2many)** — Childrens → `account.analytic.plan`
- `account_ids` **(one2many)** — Accounts → `account.analytic.account`
- `applicability_ids` **(one2many)** — Applicability → `account.analytic.applicability`

## Campos Calculados (readonly)

- `children_count` **(integer)** — Children Plans Count 🔒 readonly
- `account_count` **(integer)** — Analytic Accounts Count 🔒 readonly
- `all_account_count` **(integer)** — All Analytic Accounts Count 🔒 readonly
