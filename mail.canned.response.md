# Canned Response — `mail.canned.response`

**Ordenação padrão:** `id desc`

---

## Campos Obrigatórios

- `source` **(char)** — Shortcut ⚠️ obrigatório
  > Canned response that will automatically be substituted with longer content in your messages. Type '::' followed by the name of your shortcut (e.g. ::hello) to use in your messages.
- `substitution` **(text)** — Substitution ⚠️ obrigatório
  > Content that will automatically replace the shortcut of your choosing. This content can still be adapted before sending your message.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `last_used` **(datetime)** — Last Used
  > Last time this canned_response was used
- `is_shared` **(boolean)** — Determines if the canned_response is currently shared with other users 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `group_ids` **(many2many)** — Authorized Groups → `res.groups`

## Campos Calculados (readonly)

- `is_editable` **(boolean)** — Determines if the canned response can be edited by the current user 🔒 readonly
