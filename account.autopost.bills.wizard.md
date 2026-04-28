# Autopost Bills Wizard — `account.autopost.bills.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `nb_unmodified_bills` **(integer)** — Number of bills previously unmodified from this partner
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `partner_id` **(many2one)** — Partner → `res.partner`

## Campos Calculados (readonly)

- `partner_name` **(char)** — Name 🔒 readonly
