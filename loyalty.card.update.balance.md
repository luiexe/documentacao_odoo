# Update Loyalty Card Points — `loyalty.card.update.balance`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `card_id` **(many2one)** — Card ⚠️ obrigatório 🔒 readonly → `loyalty.card`
- `description` **(char)** — Description ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `new_balance` **(float)** — New Balance
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `old_balance` **(float)** — Points 🔒 readonly
