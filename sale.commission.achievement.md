# Manual Commission Achievement — `sale.commission.achievement`

**Ordenação padrão:** `id desc`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `date` **(date)** — Date ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `achieved` **(monetary)** — Achieved
- `currency_rate` **(float)** — Currency Rate 🔒 readonly
- `note` **(char)** — Note
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `add_user_id` **(many2one)** — Add to → `sale.commission.plan.user`
- `reduce_user_id` **(many2one)** — Reduce From → `sale.commission.plan.user`
- `currency_id` **(many2one)** — Currency → `res.currency`
