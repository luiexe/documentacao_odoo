# Grant Portal Access — `portal.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `welcome_message` **(text)** — Invitation Message
  > This text is included in the email sent to new users of the portal.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `partner_ids` **(many2many)** — Partners → `res.partner`
- `user_ids` **(one2many)** — Users → `portal.wizard.user`
