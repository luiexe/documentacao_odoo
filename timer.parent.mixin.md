# Parent Timer Mixin — `timer.parent.mixin`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly

## Relacionamentos

- `user_timer_id` **(one2many)** — User Timer 🔒 readonly → `timer.timer`

## Campos Calculados (readonly)

- `timer_start` **(datetime)** — Timer Start 🔒 readonly
- `timer_pause` **(datetime)** — Timer Last Pause 🔒 readonly
- `is_timer_running` **(boolean)** — Is Timer Running 🔒 readonly
