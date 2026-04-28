# User Settings Volumes — `res.users.settings.volumes`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `user_setting_id` **(many2one)** — User Setting ⚠️ obrigatório → `res.users.settings`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `volume` **(float)** — Volume
  > Ranges between 0.0 and 1.0, scale depends on the browser implementation
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `partner_id` **(many2one)** — Partner → `res.partner`
- `guest_id` **(many2one)** — Guest → `res.partner`
