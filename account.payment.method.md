# Payment Methods — `account.payment.method`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `code` **(char)** — Code ⚠️ obrigatório
- `payment_type` **(selection)** — Payment Type ⚠️ obrigatório
  > Opções: `inbound` (Inbound), `outbound` (Outbound)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
