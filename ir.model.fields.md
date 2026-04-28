# Fields — `ir.model.fields`

**Ordenação padrão:** `name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Field Name ⚠️ obrigatório
- `model` **(char)** — Model Name ⚠️ obrigatório
  > The technical name of the model this field belongs to
- `model_id` **(many2one)** — Model ⚠️ obrigatório → `ir.model`
  > The model this field belongs to
- `field_description` **(char)** — Field Label ⚠️ obrigatório
- `ttype` **(selection)** — Field Type ⚠️ obrigatório
  > Opções: `binary` (binary), `boolean` (boolean), `char` (char), `date` (date), `datetime` (datetime), `float` (float), `html` (html), `integer` (integer), `json` (json), `many2many` (many2many), `many2one` (many2one), `many2one_reference` (many2one_reference), `monetary` (monetary), `one2many` (one2many), `properties` (properties), `properties_definition` (properties_definition), `reference` (reference), `selection` (selection), `text` (text), `vector` (vector)
- `state` **(selection)** — Type ⚠️ obrigatório 🔒 readonly
  > Opções: `manual` (Custom Field), `base` (Base Field)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `relation` **(char)** — Related Model
  > For relationship fields, the technical name of the target model
- `relation_field` **(char)** — Relation Field
  > For one2many fields, the field on the target model that implement the opposite many2one relationship
- `help` **(text)** — Field Help
- `selection` **(char)** — Selection Options (Deprecated)
- `copied` **(boolean)** — Copied
  > Whether the value is copied when duplicating a record.
- `related` **(char)** — Related Field Definition
  > The corresponding related field, if any. This must be a dot-separated list of field names.
- `required` **(boolean)** — Required
- `readonly` **(boolean)** — Readonly
- `index` **(boolean)** — Indexed
- `translate` **(selection)** — Translatable
  > Whether values for this field can be translated (enables the translation mechanism for that field)
  > Opções: `standard` (Translate as a whole), `html_translate` (Translate HTML terms), `xml_translate` (Translate XML terms)
- `company_dependent` **(boolean)** — Company Dependent 🔒 readonly
  > Whether values for this field is company dependent
- `size` **(integer)** — Size
- `on_delete` **(selection)** — On Delete
  > On delete property for many2one fields
  > Opções: `cascade` (Cascade), `set null` (Set NULL), `restrict` (Restrict)
- `domain` **(char)** — Domain
  > The optional domain to restrict possible values for relationship fields, specified as a Python expression defining a list of triplets. For example: [('color','=','red')]
- `group_expand` **(boolean)** — Expand Groups
  > If checked, all the records of the target model will be included in a grouped result (e.g. 'Group By' filters, Kanban columns, etc.). Note that it can significantly reduce performance if the target model of the field contains a lot of records; usually used on models with few records (e.g. Stages, Job Positions, Event Types, etc.).
- `selectable` **(boolean)** — Selectable
- `relation_table` **(char)** — Relation Table
  > Used for custom many2many fields to define a custom relation table name
- `column1` **(char)** — Column 1
  > Column referring to the record in the model table
- `column2` **(char)** — Column 2
  > Column referring to the record in the comodel table
- `compute` **(text)** — Compute
  > Code to compute the value of the field. Iterate on the recordset 'self' and assign the field's value:      for record in self:         record['size'] = len(record.name)  Modules time, datetime, dateutil are available.
- `depends` **(char)** — Dependencies
  > Dependencies of compute method; a list of comma-separated field names, like      name, partner_id.name
- `store` **(boolean)** — Stored
  > Whether the value is stored in the database.
- `currency_field` **(char)** — Currency field
  > Name of the Many2one field holding the res.currency
- `sanitize` **(boolean)** — Sanitize HTML
- `sanitize_overridable` **(boolean)** — Sanitize HTML overridable
- `sanitize_tags` **(boolean)** — Sanitize HTML Tags
- `sanitize_attributes` **(boolean)** — Sanitize HTML Attributes
- `sanitize_style` **(boolean)** — Sanitize HTML Style
- `sanitize_form` **(boolean)** — Sanitize HTML Form
- `strip_style` **(boolean)** — Strip Style Attribute
- `strip_classes` **(boolean)** — Strip Class Attribute
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `tracking` **(integer)** — Enable Ordered Tracking
  > If set every modification done to this field is tracked. Value is used to order tracking values.
- `ai` **(boolean)** — AI field
  > AI computed field
- `ai_domain` **(char)** — AI field domain 🔒 readonly
- `system_prompt` **(html)** — AI Prompt
  > Prompt given to the AI model to compute the field value
- `website_form_blacklisted` **(boolean)** — Blacklisted in web forms
  > Blacklist this field for web forms

## Relacionamentos

- `relation_field_id` **(many2one)** — Relation field 🔒 readonly → `ir.model.fields`
- `selection_ids` **(one2many)** — Selection Options → `ir.model.fields.selection`
- `related_field_id` **(many2one)** — Related Field 🔒 readonly → `ir.model.fields`
- `groups` **(many2many)** — Groups → `res.groups`

## Campos Calculados (readonly)

- `modules` **(char)** — In Apps 🔒 readonly
  > List of modules in which the field is defined
