# Sign send request signer — `sign.send.request.signer`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `mail_sent_order` **(integer)** — Sign Order
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `role_id` **(many2one)** — Role 🔒 readonly → `sign.item.role`
- `partner_id` **(many2one)** — Contact → `res.partner`
- `sign_send_request_id` **(many2one)** — Sign Send Request → `sign.send.request`
