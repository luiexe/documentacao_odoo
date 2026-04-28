# Link between link previews and messages — `mail.message.link.preview`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `message_id` **(many2one)** — Message ⚠️ obrigatório → `mail.message`
- `link_preview_id` **(many2one)** — Link Preview ⚠️ obrigatório → `mail.link.preview`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `is_hidden` **(boolean)** — Is Hidden
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `author_id` **(many2one)** — Author 🔒 readonly → `res.partner`
  > Author of the message. If not set, email_from may hold an email address that did not match any partner.
