# Cancel multiple quotations — `sale.mass.cancel.orders`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `sale_order_ids` **(many2many)** — Sale orders to cancel → `sale.order`

## Campos Calculados (readonly)

- `sale_orders_count` **(integer)** — Sale Orders Count 🔒 readonly
- `has_confirmed_order` **(boolean)** — Has Confirmed Order 🔒 readonly
