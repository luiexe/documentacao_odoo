# Privacy Lookup Wizard — `privacy.lookup.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `email` **(char)** — Email ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `execution_details` **(text)** — Execution Details 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `line_ids` **(one2many)** — Line → `privacy.lookup.wizard.line`
- `log_id` **(many2one)** — Log → `privacy.log`

## Campos Calculados (readonly)

- `records_description` **(text)** — Records Description 🔒 readonly
- `line_count` **(integer)** — Line Count 🔒 readonly
