# Action Window — `ir.actions.act_window`

**Ordenação padrão:** `name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Action Name ⚠️ obrigatório
- `type` **(char)** — Action Type ⚠️ obrigatório
- `binding_type` **(selection)** — Binding Type ⚠️ obrigatório
  > Opções: `action` (Action), `report` (Report)
- `context` **(char)** — Context Value ⚠️ obrigatório
  > Context dictionary as Python expression, empty by default (Default: {})
- `res_model` **(char)** — Destination Model ⚠️ obrigatório
  > Model name of the object to open in the view window
- `view_mode` **(char)** — View Mode ⚠️ obrigatório
  > Comma-separated list of allowed view modes, such as 'form', 'list', 'calendar', etc. (Default: list,form)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `path` **(char)** — Path to show in the URL
- `help` **(html)** — Action Description
  > Optional help text for the users with a description of the target view, such as its usage and purpose.
- `binding_view_types` **(char)** — Binding View Types
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `domain` **(char)** — Domain Value
  > Optional domain filtering of the destination data, as a Python expression
- `res_id` **(integer)** — Record ID
  > Database ID of record to open in form view, when ``view_mode`` is set to 'form' only
- `target` **(selection)** — Target Window
  > Opções: `current` (Current Window), `new` (New Window), `fullscreen` (Full Screen), `main` (Main action of Current Window)
- `mobile_view_mode` **(char)** — Mobile View Mode
  > First view mode in mobile and small screen environments (default='kanban'). If it can't be found among available view modes, the same mode as for wider screens is used)
- `usage` **(char)** — Action Usage
  > Used to filter menu and home actions from the user form.
- `limit` **(integer)** — Limit
  > Default limit for the list view
- `filter` **(boolean)** — Filter
- `cache` **(boolean)** — Data Caching
  > If enabled, this action will cache the related data used in list, Kanban and form views with the aim to increase the loading speed

## Relacionamentos

- `binding_model_id` **(many2one)** — Binding Model → `ir.model`
  > Setting a value makes this action available in the sidebar for the given model.
- `view_id` **(many2one)** — View Ref. → `ir.ui.view`
- `view_ids` **(one2many)** — No of Views → `ir.actions.act_window.view`
- `group_ids` **(many2many)** — Groups → `res.groups`
- `search_view_id` **(many2one)** — Search View Ref. → `ir.ui.view`
- `embedded_action_ids` **(one2many)** — Embedded Action 🔒 readonly → `ir.embedded.actions`

## Campos Calculados (readonly)

- `xml_id` **(char)** — External ID 🔒 readonly
- `views` **(binary)** — Views 🔒 readonly
  > This function field computes the ordered list of views that should be enabled when displaying the result of an action, federating view mode, views and reference view. The result is returned as an ordered list of pairs (view_id,view_mode).
