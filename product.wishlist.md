# Product Wishlist — `product.wishlist`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `website_id` **(many2one)** — Website ⚠️ obrigatório → `website`
- `active` **(boolean)** — Active ⚠️ obrigatório
- `stock_notification` **(boolean)** — Stock Notification ⚠️ obrigatório 🔒 readonly

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `price` **(monetary)** — Price
  > Price of the product when it has been added in the wishlist
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `partner_id` **(many2one)** — Owner → `res.partner`
- `currency_id` **(many2one)** — Default Currency 🔒 readonly → `res.currency`
- `pricelist_id` **(many2one)** — Pricelist → `product.pricelist`
  > Pricelist when added
