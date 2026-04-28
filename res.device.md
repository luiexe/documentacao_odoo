# Devices — `res.device`

**Ordenação padrão:** `last_activity desc`

---

## Campos Obrigatórios

- `session_identifier` **(char)** — Session Identifier ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `platform` **(char)** — Platform
- `browser` **(char)** — Browser
- `ip_address` **(char)** — IP Address
- `country` **(char)** — Country
- `city` **(char)** — City
- `device_type` **(selection)** — Device Type
  > Opções: `computer` (Computer), `mobile` (Mobile)
- `first_activity` **(datetime)** — First Activity
- `last_activity` **(datetime)** — Last Activity
- `revoked` **(boolean)** — Revoked
  > If True, the session file corresponding to this device                                     no longer exists on the filesystem.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — User → `res.users`

## Campos Calculados (readonly)

- `is_current` **(boolean)** — Current Device 🔒 readonly
- `linked_ip_addresses` **(text)** — Linked IP address 🔒 readonly
