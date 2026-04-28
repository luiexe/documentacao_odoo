# Studio Export Data — `studio.export.wizard.data`

**Ordenação padrão:** `model_name, res_id`

---

## Campos Obrigatórios

- `model` **(char)** — Model ⚠️ obrigatório
- `res_id` **(many2one_reference)** — Res ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `model_name` **(char)** — Model Description 🔒 readonly
- `name` **(char)** — Record Name 🔒 readonly
- `xmlid` **(char)** — External ID 🔒 readonly
- `pre` **(boolean)** — Pre 🔒 readonly
- `post` **(boolean)** — Post 🔒 readonly
- `studio` **(boolean)** — Studio 🔒 readonly
- `is_demo_data` **(boolean)** — As Demo 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
