# Purchases & Bills Union — `purchase.bill.union`

**Ordenação padrão:** `date desc, name desc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Reference 🔒 readonly
- `reference` **(char)** — Source 🔒 readonly
- `date` **(date)** — Date 🔒 readonly
- `amount` **(float)** — Amount 🔒 readonly

## Relacionamentos

- `partner_id` **(many2one)** — Vendor 🔒 readonly → `res.partner`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `vendor_bill_id` **(many2one)** — Vendor Bill 🔒 readonly → `account.move`
- `purchase_order_id` **(many2one)** — Purchase Order 🔒 readonly → `purchase.order`
