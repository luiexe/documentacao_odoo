# Mailing Favorite Filters — `mailing.filter`

**Ordenação padrão:** `create_date DESC`

---

## Campos Obrigatórios

- `name` **(char)** — Filter Name ⚠️ obrigatório
- `mailing_domain` **(char)** — Filter Domain ⚠️ obrigatório
- `mailing_model_id` **(many2one)** — Recipients Model ⚠️ obrigatório → `ir.model`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `mailing_model_name` **(char)** — Recipients Model Name 🔒 readonly
