# Horizontal group for reports — `account.report.horizontal.group`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `rule_ids` **(one2many)** — Rules ⚠️ obrigatório → `account.report.horizontal.group.rule`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `report_ids` **(many2many)** — Reports → `account.report`
