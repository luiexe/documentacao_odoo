# Delivery Carrier Selection Wizard — `choose.delivery.carrier`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `order_id` **(many2one)** — Order ⚠️ obrigatório → `sale.order`
- `partner_id` **(many2one)** — Customer ⚠️ obrigatório 🔒 readonly → `res.partner`
- `carrier_id` **(many2one)** — Shipping Method ⚠️ obrigatório → `delivery.carrier`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `delivery_price` **(float)** — Delivery Price
- `display_price` **(float)** — Cost 🔒 readonly
- `delivery_message` **(text)** — Delivery Message 🔒 readonly
- `total_weight` **(float)** — Total Order Weight
- `weight_uom_name` **(char)** — Weight Uom Name 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `available_carrier_ids` **(many2many)** — Available Carriers 🔒 readonly → `delivery.carrier`

## Campos Calculados (readonly)

- `delivery_type` **(selection)** — Provider 🔒 readonly
  > Opções: `base_on_rule` (Based on Rules), `fixed` (Fixed Price), `envia` (Envia), `in_store` (Pick up in store)
- `invoicing_message` **(text)** — Invoicing Message 🔒 readonly
