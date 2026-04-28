# Model Constraint — `ir.model.constraint`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Constraint ⚠️ obrigatório 🔒 readonly
  > PostgreSQL constraint or foreign key name.
- `model` **(many2one)** — Model ⚠️ obrigatório 🔒 readonly → `ir.model`
- `module` **(many2one)** — Module ⚠️ obrigatório 🔒 readonly → `ir.module.module`
- `type` **(char)** — Constraint Type ⚠️ obrigatório 🔒 readonly
  > Type of the constraint: `f` for a foreign key, `u` for other constraints.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `definition` **(char)** — Definition 🔒 readonly
  > PostgreSQL constraint definition
- `message` **(char)** — Message
  > Error message returned when the constraint is violated.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
