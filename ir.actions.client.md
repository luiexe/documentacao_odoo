# Client Action — `ir.actions.client`

**Ordenação padrão:** `name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Action Name ⚠️ obrigatório
- `type` **(char)** — Action Type ⚠️ obrigatório
- `binding_type` **(selection)** — Binding Type ⚠️ obrigatório
  > Opções: `action` (Action), `report` (Report)
- `tag` **(char)** — Client action tag ⚠️ obrigatório
  > An arbitrary string, interpreted by the client according to its own needs and wishes. There is no central tag repository across clients.
- `context` **(char)** — Context Value ⚠️ obrigatório
  > Context dictionary as Python expression, empty by default (Default: {})

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `path` **(char)** — Path to show in the URL
- `help` **(html)** — Action Description
  > Optional help text for the users with a description of the target view, such as its usage and purpose.
- `binding_view_types` **(char)** — Binding View Types
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `target` **(selection)** — Target Window
  > Opções: `current` (Current Window), `new` (New Window), `fullscreen` (Full Screen), `main` (Main action of Current Window)
- `res_model` **(char)** — Destination Model
  > Optional model, mostly used for needactions.
- `params` **(binary)** — Supplementary arguments
  > Arguments sent to the client along with the view tag
- `params_store` **(binary)** — Params storage 🔒 readonly

## Relacionamentos

- `binding_model_id` **(many2one)** — Binding Model → `ir.model`
  > Setting a value makes this action available in the sidebar for the given model.

## Campos Calculados (readonly)

- `xml_id` **(char)** — External ID 🔒 readonly
