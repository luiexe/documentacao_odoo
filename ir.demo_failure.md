# Demo failure — `ir.demo_failure`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `module_id` **(many2one)** — Module ⚠️ obrigatório → `ir.module.module`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `error` **(char)** — Error
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `wizard_id` **(many2one)** — Wizard → `ir.demo_failure.wizard`
