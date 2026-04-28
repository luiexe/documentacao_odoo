# Add Contacts to Mailing List — `mailing.contact.to.list`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `mailing_list_id` **(many2one)** — Mailing List ⚠️ obrigatório → `mailing.list`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `contact_ids` **(many2many)** — Contacts → `mailing.contact`
