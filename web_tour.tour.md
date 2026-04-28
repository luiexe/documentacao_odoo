# Tours — `web_tour.tour`

**Ordenação padrão:** `sequence, name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `url` **(char)** — Starting URL
- `rainbow_man_message` **(html)** — Rainbow Man Message
- `sequence` **(integer)** — Sequence
- `custom` **(boolean)** — Custom
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `step_ids` **(one2many)** — Step → `web_tour.tour.step`
- `user_consumed_ids` **(many2many)** — User Consumed → `res.users`

## Campos Calculados (readonly)

- `sharing_url` **(char)** — Sharing URL 🔒 readonly
