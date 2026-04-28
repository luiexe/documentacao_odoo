# Privacy Log — `privacy.log`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `date` **(datetime)** — Date ⚠️ obrigatório
- `anonymized_name` **(char)** — Anonymized Name ⚠️ obrigatório
- `anonymized_email` **(char)** — Anonymized Email ⚠️ obrigatório
- `user_id` **(many2one)** — Handled By ⚠️ obrigatório → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `execution_details` **(text)** — Execution Details
- `records_description` **(text)** — Found Records
- `additional_note` **(text)** — Additional Note
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
