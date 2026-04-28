# Report Action — `ir.actions.report`

**Ordenação padrão:** `name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Action Name ⚠️ obrigatório
- `type` **(char)** — Action Type ⚠️ obrigatório
- `binding_type` **(selection)** — Binding Type ⚠️ obrigatório
  > Opções: `action` (Action), `report` (Report)
- `model` **(char)** — Model Name ⚠️ obrigatório
- `report_type` **(selection)** — Report Type ⚠️ obrigatório
  > The type of the report that will be rendered, each one having its own rendering method. HTML means the report will be opened directly in your browser PDF means the report will be rendered using Wkhtmltopdf and downloaded by the user.
  > Opções: `qweb-html` (HTML), `qweb-pdf` (PDF), `qweb-text` (Text)
- `report_name` **(char)** — Template Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `path` **(char)** — Path to show in the URL
- `help` **(html)** — Action Description
  > Optional help text for the users with a description of the target view, such as its usage and purpose.
- `binding_view_types` **(char)** — Binding View Types
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `report_file` **(char)** — Report File
  > The path to the main report file (depending on Report Type) or empty if the content is in another field
- `multi` **(boolean)** — On Multiple Doc.
  > If set to true, the action will not be displayed on the right toolbar of a form view.
- `print_report_name` **(char)** — Printed Report Name
  > This is the filename of the report going to download. Keep empty to not change the report filename. You can use a python expression with the 'object' and 'time' variables.
- `attachment_use` **(boolean)** — Reload from Attachment
  > If enabled, then the second time the user prints with same attachment name, it returns the previous report.
- `attachment` **(char)** — Save as Attachment Prefix
  > This is the filename of the attachment used to store the printing result. Keep empty to not save the printed reports. You can use a python expression with the object and time variables.
- `domain` **(char)** — Filter domain
  > If set, the action will only appear on records that matches the domain.
- `is_invoice_report` **(boolean)** — Invoice report

## Relacionamentos

- `binding_model_id` **(many2one)** — Binding Model → `ir.model`
  > Setting a value makes this action available in the sidebar for the given model.
- `model_id` **(many2one)** — Model 🔒 readonly → `ir.model`
- `group_ids` **(many2many)** — Groups → `res.groups`
- `paperformat_id` **(many2one)** — Paper Format → `report.paperformat`

## Campos Calculados (readonly)

- `xml_id` **(char)** — External ID 🔒 readonly
