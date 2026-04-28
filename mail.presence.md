# User/Guest Presence — `mail.presence`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `last_poll` **(datetime)** — Last Poll
- `last_presence` **(datetime)** — Last Presence
- `status` **(selection)** — IM Status
  > Opções: `online` (Online), `away` (Away), `offline` (Offline)

## Relacionamentos

- `user_id` **(many2one)** — Users → `res.users`
- `guest_id` **(many2one)** — Guest → `mail.guest`
