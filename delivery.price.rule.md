# Delivery Price Rules — `delivery.price.rule`

**Ordenação padrão:** `sequence, list_price, id`

---

## Campos Obrigatórios

- `sequence` **(integer)** — Sequence ⚠️ obrigatório
- `carrier_id` **(many2one)** — Carrier ⚠️ obrigatório → `delivery.carrier`
- `variable` **(selection)** — Variable ⚠️ obrigatório
  > Opções: `weight` (Weight), `volume` (Volume), `wv` (Weight * Volume), `price` (Price), `quantity` (Quantity)
- `operator` **(selection)** — Operator ⚠️ obrigatório
  > Opções: `==` (=), `<=` (<=), `<` (<), `>=` (>=), `>` (>)
- `max_value` **(float)** — Maximum Value ⚠️ obrigatório
- `list_base_price` **(float)** — Sale Base Price ⚠️ obrigatório
- `list_price` **(float)** — Sale Price ⚠️ obrigatório
- `variable_factor` **(selection)** — Variable Factor ⚠️ obrigatório
  > Opções: `weight` (Weight), `volume` (Volume), `wv` (Weight * Volume), `price` (Price), `quantity` (Quantity)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `name` **(char)** — Name 🔒 readonly
