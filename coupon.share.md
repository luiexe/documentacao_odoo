# Create links that apply a coupon and redirect to a specific page — `coupon.share`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `website_id` **(many2one)** — Website ⚠️ obrigatório → `website`
- `program_id` **(many2one)** — Program ⚠️ obrigatório → `loyalty.program`
- `redirect` **(char)** — Redirect ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `coupon_id` **(many2one)** — Coupon → `loyalty.card`
- `program_website_id` **(many2one)** — Program Website 🔒 readonly → `website`
  > Restrict to a specific website.

## Campos Calculados (readonly)

- `promo_code` **(char)** — Promo Code 🔒 readonly
- `share_link` **(char)** — Share Link 🔒 readonly
