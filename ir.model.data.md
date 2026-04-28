# Model Data — `ir.model.data`

**Ordenação padrão:** `module, model, name`

---

## Campos Obrigatórios

- `name` **(char)** — External Identifier ⚠️ obrigatório
  > External Key/Identifier that can be used for data integration with third-party systems
- `model` **(char)** — Model Name ⚠️ obrigatório
- `module` **(char)** — Module ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `res_id` **(many2one_reference)** — Record ID
  > ID of the target record in the database
- `noupdate` **(boolean)** — Non Updatable
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `studio` **(boolean)** — Studio
  > Checked if it has been edited with Studio.

## Campos Calculados (readonly)

- `complete_name` **(char)** — Complete ID 🔒 readonly
- `reference` **(char)** — Reference 🔒 readonly
