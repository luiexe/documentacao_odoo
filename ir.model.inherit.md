# Model Inheritance Tree — `ir.model.inherit`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `model_id` **(many2one)** — Model ⚠️ obrigatório → `ir.model`
- `parent_id` **(many2one)** — Parent ⚠️ obrigatório → `ir.model`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly

## Relacionamentos

- `parent_field_id` **(many2one)** — Parent Field → `ir.model.fields`
