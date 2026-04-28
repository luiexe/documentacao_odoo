# Keep the call history — `discuss.call.history`

**Ordenação padrão:** `start_dt DESC, id DESC`

---

## Campos Obrigatórios

- `channel_id` **(many2one)** — Channel ⚠️ obrigatório → `discuss.channel`
- `start_dt` **(datetime)** — Start Dt ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `end_dt` **(datetime)** — End Dt
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `start_call_message_id` **(many2one)** — Start Call Message → `mail.message`

## Campos Calculados (readonly)

- `duration_hour` **(float)** — Duration Hour 🔒 readonly
