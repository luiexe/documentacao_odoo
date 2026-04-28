# Demo Failure wizard — `ir.demo_failure.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `failure_ids` **(one2many)** — Demo Installation Failures 🔒 readonly → `ir.demo_failure`

## Campos Calculados (readonly)

- `failures_count` **(integer)** — Failures Count 🔒 readonly
