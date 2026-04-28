# Timer Module — `timer.timer`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `res_model` **(char)** — Res Model ⚠️ obrigatório
- `res_id` **(integer)** — Res ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `timer_start` **(datetime)** — Timer Start
- `timer_pause` **(datetime)** — Timer Last Pause
- `parent_res_model` **(char)** — Parent Document Model
- `parent_res_id` **(integer)** — Parent Document
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — User → `res.users`

## Campos Calculados (readonly)

- `is_timer_running` **(boolean)** — Is Timer Running 🔒 readonly
