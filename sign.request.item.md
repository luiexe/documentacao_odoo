# Signature Request Item — `sign.request.item`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `access_token` **(char)** — Security Token ⚠️ obrigatório 🔒 readonly
- `sign_request_id` **(many2one)** — Signature Request ⚠️ obrigatório → `sign.request`
- `role_id` **(many2one)** — Role ⚠️ obrigatório 🔒 readonly → `sign.item.role`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `mail_sent_order` **(integer)** — Mail Sent Order
- `access_via_link` **(boolean)** — Accessed Through Token
- `sms_number` **(char)** — Phone
- `sms_token` **(char)** — SMS Token 🔒 readonly
- `signed_without_extra_auth` **(boolean)** — Signed Without Extra Authentication 🔒 readonly
- `signature` **(binary)** — Signature
- `signing_date` **(date)** — Signed on 🔒 readonly
- `state` **(selection)** — State 🔒 readonly
  > Opções: `sent` (To Sign), `completed` (Signed), `canceled` (Cancelled)
- `signer_email` **(char)** — Email 🔒 readonly
- `is_mail_sent` **(boolean)** — Is Mail Sent 🔒 readonly
  > The signature mail has been sent.
- `latitude` **(float)** — Latitude
- `longitude` **(float)** — Longitude
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `sign_link` **(char)** — Sign Link

## Relacionamentos

- `partner_id` **(many2one)** — Signer → `res.partner`
- `sign_item_value_ids` **(one2many)** — Value → `sign.request.item.value`
- `communication_company_id` **(many2one)** — Company used for communication 🔒 readonly → `res.company`

## Campos Calculados (readonly)

- `access_url` **(char)** — Portal Access URL 🔒 readonly
  > Customer Portal URL
- `access_warning` **(text)** — Access warning 🔒 readonly
- `reference` **(char)** — Document Name 🔒 readonly
  > This is how the document will be named in the mail
- `frame_hash` **(char)** — Frame Hash 🔒 readonly
- `color` **(integer)** — Color 🔒 readonly
- `change_authorized` **(boolean)** — Change Authorized 🔒 readonly
  > If checked, recipient of a document with this role can be changed after having sent the request. Useful to replace a signatory who is out of office, etc.
- `document_link` **(char)** — Document Link 🔒 readonly
- `attachments_download_link` **(char)** — Attachments Download Link 🔒 readonly
