# Rating Mixin — `rating.mixin`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `rating_last_value` **(float)** — Rating Last Value 🔒 readonly

## Campos Calculados (readonly)

- `rating_last_feedback` **(text)** — Rating Last Feedback 🔒 readonly
- `rating_last_image` **(binary)** — Rating Last Image 🔒 readonly
- `rating_count` **(integer)** — Rating count 🔒 readonly
- `rating_avg` **(float)** — Average Rating 🔒 readonly
- `rating_avg_text` **(selection)** — Rating Avg Text 🔒 readonly
  > Opções: `top` (Happy), `ok` (Neutral), `ko` (Unhappy), `none` (Not Rated yet)
- `rating_percentage_satisfaction` **(float)** — Rating Satisfaction 🔒 readonly
- `rating_last_text` **(selection)** — Rating Text 🔒 readonly
  > Opções: `top` (Happy), `ok` (Neutral), `ko` (Unhappy), `none` (Not Rated yet)
