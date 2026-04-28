# Website Configurator Feature — `website.configurator.feature`

**Ordenação padrão:** `sequence`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `name` **(char)** — Name
- `description` **(char)** — Description
- `icon` **(char)** — Icon
- `iap_page_code` **(char)** — Iap Page Code
  > Page code used to tell IAP website_service for which page a snippet list should be generated
- `website_config_preselection` **(char)** — Website Config Preselection
  > Comma-separated list of website type/purpose for which this feature should be pre-selected
- `feature_url` **(char)** — Feature Url
- `menu_sequence` **(integer)** — Menu Sequence
  > If set, a website menu will be created for the feature.
- `menu_company` **(boolean)** — Menu Company
  > If set, add the menu as a second level menu, as a child of "Company" menu.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `page_view_id` **(many2one)** — Page View → `ir.ui.view`
- `module_id` **(many2one)** — Module → `ir.module.module`
