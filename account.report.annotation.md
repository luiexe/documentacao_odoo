# Account Report Annotation — `account.report.annotation`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `message_id` **(many2one)** — Message ⚠️ obrigatório → `mail.message`
- `date` **(date)** — Date ⚠️ obrigatório
  > Date considered as annotated by the annotation.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
