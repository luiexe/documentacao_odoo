# Signature Item Value — `sign.request.item.value`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `sign_request_item_id` **(many2one)** — Signature Request item ⚠️ obrigatório → `sign.request.item`
- `sign_item_id` **(many2one)** — Signature Item ⚠️ obrigatório → `sign.item`
- `sign_request_id` **(many2one)** — Signature Request ⚠️ obrigatório 🔒 readonly → `sign.request`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `value` **(text)** — Value
- `frame_value` **(text)** — Frame Value
- `frame_has_hash` **(boolean)** — Frame Has Hash
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
