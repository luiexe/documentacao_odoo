# Action URL — `ir.actions.act_url`

**Ordenação padrão:** `name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Action Name ⚠️ obrigatório
- `type` **(char)** — Action Type ⚠️ obrigatório
- `binding_type` **(selection)** — Binding Type ⚠️ obrigatório
  > Opções: `action` (Action), `report` (Report)
- `url` **(text)** — Action URL ⚠️ obrigatório
- `target` **(selection)** — Action Target ⚠️ obrigatório
  > Opções: `new` (New Window), `self` (This Window), `download` (Download)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `path` **(char)** — Path to show in the URL
- `help` **(html)** — Action Description
  > Optional help text for the users with a description of the target view, such as its usage and purpose.
- `binding_view_types` **(char)** — Binding View Types
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `binding_model_id` **(many2one)** — Binding Model → `ir.model`
  > Setting a value makes this action available in the sidebar for the given model.

## Campos Calculados (readonly)

- `xml_id` **(char)** — External ID 🔒 readonly
