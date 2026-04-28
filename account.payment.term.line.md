# Payment Terms Line — `account.payment.term.line`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `value` **(selection)** — Value ⚠️ obrigatório
  > Select here the kind of valuation related to this payment terms line.
  > Opções: `percent` (Percent), `fixed` (Fixed)
- `delay_type` **(selection)** — Delay Type ⚠️ obrigatório
  > Opções: `days_after` (Days after invoice date), `days_after_end_of_month` (Days after end of month), `days_after_end_of_next_month` (Days after end of next month), `days_end_of_month_on_the` (Days end of month on the)
- `payment_id` **(many2one)** — Payment Terms ⚠️ obrigatório → `account.payment.term`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `value_amount` **(float)** — Due
  > For percent enter a ratio between 0-100.
- `days_next_month` **(char)** — Days on the next month
- `nb_days` **(integer)** — Days
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `display_days_next_month` **(boolean)** — Display Days Next Month 🔒 readonly
