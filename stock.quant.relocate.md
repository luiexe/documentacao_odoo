# Stock Quantity Relocation — `stock.quant.relocate`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `message` **(text)** — Reason for relocation
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `quant_ids` **(many2many)** — Quant → `stock.quant`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
  > Let this field empty if this location is shared between companies
- `dest_location_id` **(many2one)** — Dest Location → `stock.location`
- `dest_package_id` **(many2one)** — Dest Package 🔒 readonly → `stock.package`

## Campos Calculados (readonly)

- `dest_package_id_domain` **(char)** — Dest Package Id Domain 🔒 readonly
- `is_partial_package` **(boolean)** — Is Partial Package 🔒 readonly
- `partial_package_names` **(char)** — Partial Package Names 🔒 readonly
- `is_multi_location` **(boolean)** — Is Multi Location 🔒 readonly
