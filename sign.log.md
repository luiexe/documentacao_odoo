# Sign requests access history — `sign.log`

**Ordenação padrão:** `log_date, id`

---

## Campos Obrigatórios

- `log_date` **(datetime)** — Log Date ⚠️ obrigatório
- `sign_request_id` **(many2one)** — Sign Request ⚠️ obrigatório → `sign.request`
- `ip` **(char)** — IP address of the visitor ⚠️ obrigatório
- `action` **(selection)** — Action Performed ⚠️ obrigatório
  > Opções: `create` (Creation), `open` (View/Download), `save` (Save), `sign` (Signature), `refuse` (Refuse), `cancel` (Cancel), `update_mail` (Mail Update), `update` (Update)
- `request_state` **(selection)** — State of the request on action log ⚠️ obrigatório
  > Opções: `shared` (Shared), `sent` (Before Signature), `signed` (After Signature), `refused` (Refused Signature), `canceled` (Cancelled), `expired` (Expired)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `latitude` **(float)** — Latitude
- `longitude` **(float)** — Longitude
- `log_hash` **(char)** — Inalterability Hash 🔒 readonly
- `token` **(char)** — User token
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `sign_request_item_id` **(many2one)** — Sign Request Item → `sign.request.item`
- `user_id` **(many2one)** — User → `res.users`
- `partner_id` **(many2one)** — Partner → `res.partner`
