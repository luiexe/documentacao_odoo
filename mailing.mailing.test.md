# Sample Mail Wizard — `mailing.mailing.test`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `email_to` **(text)** — Recipients ⚠️ obrigatório
  > Carriage-return-separated list of email addresses.
- `mass_mailing_id` **(many2one)** — Mailing ⚠️ obrigatório → `mailing.mailing`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
