# Signature Item Role — `sign.item.role`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `default` **(boolean)** — Default ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Default order
- `auth_method` **(selection)** — Extra Authentication Step
  > Force the signatory to identify using a second authentication method
  > Opções: `sms` (Unique Code via SMS)
- `change_authorized` **(boolean)** — Change Authorized
  > If checked, recipient of a document with this role can be changed after having sent the request. Useful to replace a signatory who is out of office, etc.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `assign_to` **(many2one)** — Assign to → `res.partner`
  > assign the current user or the customer as a signer by default
