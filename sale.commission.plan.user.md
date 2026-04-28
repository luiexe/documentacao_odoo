# Commission Plan User — `sale.commission.plan.user`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `plan_id` **(many2one)** — Plan ⚠️ obrigatório → `sale.commission.plan`
- `user_id` **(many2one)** — Salesperson ⚠️ obrigatório → `res.users`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date_from` **(date)** — From
- `date_to` **(date)** — To
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `other_plans` **(many2many)** — Other plans → `sale.commission.plan`
