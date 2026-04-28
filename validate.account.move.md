# Validate Account Move — `validate.account.move`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `force_post` **(boolean)** — Force
  > Entries in the future are set to be auto-posted by default. Check this checkbox to post them now.
- `force_hash` **(boolean)** — Force Hash
- `ignore_abnormal_date` **(boolean)** — Ignore Abnormal Date
- `ignore_abnormal_amount` **(boolean)** — Ignore Abnormal Amount
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `move_ids` **(many2many)** — Move → `account.move`
- `abnormal_date_partner_ids` **(one2many)** — Abnormal Date Partner 🔒 readonly → `res.partner`
- `abnormal_amount_partner_ids` **(one2many)** — Abnormal Amount Partner 🔒 readonly → `res.partner`

## Campos Calculados (readonly)

- `display_force_post` **(boolean)** — Display Force Post 🔒 readonly
- `display_force_hash` **(boolean)** — Display Force Hash 🔒 readonly
- `is_entries` **(boolean)** — Is Entries 🔒 readonly
