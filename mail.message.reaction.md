# Message Reaction — `mail.message.reaction`

**Ordenação padrão:** `id desc`

---

## Campos Obrigatórios

- `message_id` **(many2one)** — Message ⚠️ obrigatório 🔒 readonly → `mail.message`
- `content` **(char)** — Content ⚠️ obrigatório 🔒 readonly

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly

## Relacionamentos

- `partner_id` **(many2one)** — Reacting Partner 🔒 readonly → `res.partner`
- `guest_id` **(many2one)** — Reacting Guest 🔒 readonly → `mail.guest`
