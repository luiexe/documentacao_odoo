# Visited Pages — `website.track`

**Ordenação padrão:** `visit_datetime DESC`

---

## Campos Obrigatórios

- `visitor_id` **(many2one)** — Visitor ⚠️ obrigatório 🔒 readonly → `website.visitor`
- `visit_datetime` **(datetime)** — Visit Date ⚠️ obrigatório 🔒 readonly

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `url` **(text)** — Url

## Relacionamentos

- `page_id` **(many2one)** — Page 🔒 readonly → `website.page`
- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
