# Mailing Contact Import — `mailing.contact.import`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `contact_list` **(text)** — Contact List
  > Contact list that will be imported, one contact per line
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `mailing_list_ids` **(many2many)** — Lists → `mailing.list`
