# Package — `stock.package`

**Ordenação padrão:** `name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Package Reference ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `complete_name` **(char)** — Full Package Name 🔒 readonly
- `shipping_weight` **(float)** — Shipping Weight
  > Total weight of the package.
- `pack_date` **(date)** — Pack Date
- `parent_path` **(char)** — Parent Path
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `quant_ids` **(one2many)** — Bulk Content 🔒 readonly → `stock.quant`
- `contained_quant_ids` **(one2many)** — Contained Quant 🔒 readonly → `stock.quant`
- `package_type_id` **(many2one)** — Package Type → `stock.package.type`
- `location_id` **(many2one)** — Location → `stock.location`
- `location_dest_id` **(many2one)** — Destination location 🔒 readonly → `stock.location`
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `owner_id` **(many2one)** — Owner 🔒 readonly → `res.partner`
- `parent_package_id` **(many2one)** — Container → `stock.package`
- `child_package_ids` **(one2many)** — Contained Packages → `stock.package`
- `all_children_package_ids` **(one2many)** — All Children Package 🔒 readonly → `stock.package`
- `package_dest_id` **(many2one)** — Destination Container → `stock.package`
- `outermost_package_id` **(many2one)** — Outermost Destination Container 🔒 readonly → `stock.package`
- `child_package_dest_ids` **(one2many)** — Assigned Contained Packages → `stock.package`
- `move_line_ids` **(one2many)** — Move Line 🔒 readonly → `stock.move.line`
- `picking_ids` **(many2many)** — Transfers 🔒 readonly → `stock.picking`
  > Transfers in which the Package is set as Destination Package
- `l10n_br_move_id` **(many2one)** — L10N Br Move → `account.move`
  > Technical field that assigns this package to an invoice for Brazilian EDI.

## Campos Calculados (readonly)

- `dest_complete_name` **(char)** — Package Name At Destination 🔒 readonly
- `content_description` **(char)** — Contents 🔒 readonly
- `valid_sscc` **(boolean)** — Package name is valid SSCC 🔒 readonly
- `json_popover` **(char)** — JSON data for popover widget 🔒 readonly
- `weight` **(float)** — Weight 🔒 readonly
  > Total weight of all the products contained in the package.
- `weight_uom_name` **(char)** — Weight unit of measure label 🔒 readonly
- `weight_is_kg` **(boolean)** — Technical field indicating whether weight uom is kg or not (i.e. lb) 🔒 readonly
- `weight_uom_rounding` **(float)** — Technical field indicating weight's number of decimal places 🔒 readonly
- `package_carrier_type` **(selection)** — Carrier 🔒 readonly
  > Opções: `none` (No carrier integration), `envia` (Envia)
