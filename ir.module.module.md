# Module — `ir.module.module`

**Ordenação padrão:** `application desc,sequence,name`

---

## Campos Obrigatórios

- `name` **(char)** — Technical Name ⚠️ obrigatório 🔒 readonly

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `shortdesc` **(char)** — Module Name 🔒 readonly
- `summary` **(char)** — Summary 🔒 readonly
- `description` **(text)** — Description 🔒 readonly
- `author` **(char)** — Author 🔒 readonly
- `maintainer` **(char)** — Maintainer 🔒 readonly
- `contributors` **(text)** — Contributors 🔒 readonly
- `website` **(char)** — Website 🔒 readonly
- `latest_version` **(char)** — Installed Version 🔒 readonly
- `published_version` **(char)** — Published Version 🔒 readonly
- `url` **(char)** — URL 🔒 readonly
- `sequence` **(integer)** — Sequence
- `auto_install` **(boolean)** — Automatic Installation
  > An auto-installable module is automatically installed by the system when all its dependencies are satisfied. If the module has no dependency, it is always installed.
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `uninstallable` (Uninstallable), `uninstalled` (Not Installed), `installed` (Installed), `to upgrade` (To be upgraded), `to remove` (To be removed), `to install` (To be installed)
- `demo` **(boolean)** — Demo Data 🔒 readonly
- `license` **(selection)** — License 🔒 readonly
  > Opções: `GPL-2` (GPL Version 2), `GPL-2 or any later version` (GPL-2 or later version), `GPL-3` (GPL Version 3), `GPL-3 or any later version` (GPL-3 or later version), `AGPL-3` (Affero GPL-3), `LGPL-3` (LGPL Version 3), `Other OSI approved licence` (Other OSI Approved License), `OEEL-1` (Odoo Enterprise Edition License v1.0), `OPL-1` (Odoo Proprietary License v1.0), `Other proprietary` (Other Proprietary)
- `menus_by_module` **(text)** — Menus 🔒 readonly
- `reports_by_module` **(text)** — Reports 🔒 readonly
- `views_by_module` **(text)** — Views 🔒 readonly
- `application` **(boolean)** — Application 🔒 readonly
- `icon` **(char)** — Icon URL
- `to_buy` **(boolean)** — Odoo Enterprise Module
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `imported` **(boolean)** — Imported Module
- `module_type` **(selection)** — Module Type
  > Opções: `official` (Official Apps), `industries` (Industries)

## Relacionamentos

- `category_id` **(many2one)** — Category 🔒 readonly → `ir.module.category`
- `dependencies_id` **(one2many)** — Dependencies 🔒 readonly → `ir.module.module.dependency`
- `country_ids` **(many2many)** — Country → `res.country`
- `exclusion_ids` **(one2many)** — Exclusions 🔒 readonly → `ir.module.module.exclusion`
- `image_ids` **(one2many)** — Screenshots 🔒 readonly → `ir.attachment`

## Campos Calculados (readonly)

- `description_html` **(html)** — Description HTML 🔒 readonly
- `installed_version` **(char)** — Latest Version 🔒 readonly
- `icon_image` **(binary)** — Icon 🔒 readonly
- `icon_flag` **(char)** — Flag 🔒 readonly
- `has_iap` **(boolean)** — Has Iap 🔒 readonly
- `is_module_official` **(boolean)** — Is Module Official 🔒 readonly
- `account_templates` **(binary)** — Account Templates 🔒 readonly
- `is_installed_on_current_website` **(boolean)** — Is Installed On Current Website 🔒 readonly
