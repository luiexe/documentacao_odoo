# Job Platforms — `hr.job.platform`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `email` **(char)** — Email ⚠️ obrigatório
  > Applications received from this Email won't be linked to a contact.There will be no email address set on the Applicant either.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `regex` **(char)** — Regex
  > The regex facilitates to extract information from the subject or body of the received email to autopopulate the Applicant's name field
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
