# Allow profiling only to Tech Support level — `ir.profile`

**Ordenação padrão:** `session desc, id desc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Creation Date
- `session` **(char)** — Session
- `name` **(char)** — Description
- `duration` **(float)** — Duration
  > Real elapsed time
- `cpu_duration` **(float)** — CPU Duration
  > CPU clock (not including other processes or SQL)
- `init_stack_trace` **(text)** — Initial stack trace
- `sql` **(text)** — Sql
- `sql_count` **(integer)** — Queries Count
- `traces_async` **(text)** — Traces Async
- `traces_sync` **(text)** — Traces Sync
- `others` **(text)** — others
- `qweb` **(text)** — Qweb
- `entry_count` **(integer)** — Entry count

## Campos Calculados (readonly)

- `speedscope` **(binary)** — Speedscope 🔒 readonly
- `speedscope_url` **(text)** — Open 🔒 readonly
- `config_url` **(text)** — Open profiles config 🔒 readonly
