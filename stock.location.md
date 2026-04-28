# Inventory Locations — `stock.location`

**Ordenação padrão:** `complete_name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Location Name ⚠️ obrigatório
- `usage` **(selection)** — Location Type ⚠️ obrigatório
  > * Vendor: Virtual location representing the source location for products coming from your vendors * Virtual: Virtual location used to create a hierarchical structure for your warehouse by aggregating its child locations. Can't directly contain products * Internal: Physical locations inside your warehouses, * Customer: Virtual location representing the destination location for products sent to your customers * Inventory Loss: Virtual location serving as the counterpart for inventory operations done to correct stock levels (Physical inventories) * Production: Virtual counterpart location for production operations. I.e. This location consumes components and produces finished products * Transit: Counterpart location that should be used for inter-company or inter-warehouses operations
  > Opções: `supplier` (Vendor), `view` (Virtual), `internal` (Internal), `customer` (Customer), `inventory` (Inventory Loss), `production` (Production), `transit` (Transit)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `complete_name` **(char)** — Full Location Name 🔒 readonly
- `active` **(boolean)** — Active
  > By unchecking the active field, you may hide a location without deleting it.
- `parent_path` **(char)** — Parent Path
- `replenish_location` **(boolean)** — Replenishments
  > Trigger replenishment suggestions for this location when required
- `barcode` **(char)** — Barcode
- `cyclic_inventory_frequency` **(integer)** — Inventory Frequency
  >  When different than 0, inventory count date for products stored at this location will be automatically set at the defined frequency.
- `last_inventory_date` **(date)** — Last Inventory 🔒 readonly
  > Date of the last inventory at this location.
- `next_inventory_date` **(date)** — Next Expected 🔒 readonly
  > Date for next planned inventory based on cyclic schedule.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `location_id` **(many2one)** — Parent Location → `stock.location`
  > The parent location that includes this location. Example : The 'Dispatch Zone' is the 'Gate 1' parent location.
- `child_ids` **(one2many)** — Contains → `stock.location`
- `child_internal_location_ids` **(many2many)** — Internal locations among descendants 🔒 readonly → `stock.location`
  > This location (if it's internal) and all its descendants filtered by type=Internal.
- `company_id` **(many2one)** — Company → `res.company`
  > Let this field empty if this location is shared between companies
- `removal_strategy_id` **(many2one)** — Removal Strategy → `product.removal`
  > Defines the default method used for suggesting the exact location (shelf) where to take the products from, which lot etc. for this location. This method can be enforced at the product category level, and a fallback is made on the parent locations if none is set here.  FIFO: products/lots that were stocked first will be moved out first. LIFO: products/lots that were stocked last will be moved out first. Closest Location: products/lots closest to the target location will be moved out first. Least Packages: products/lots that were stocked in package with least amount of qty will be moved out first. FEFO: products/lots with the closest removal date will be moved out first (the availability of this method depends on the "Expiration Dates" setting).
- `putaway_rule_ids` **(one2many)** — Putaway Rules → `stock.putaway.rule`
- `quant_ids` **(one2many)** — Quant → `stock.quant`
- `warehouse_view_ids` **(one2many)** — Warehouse View 🔒 readonly → `stock.warehouse`
- `warehouse_id` **(many2one)** — Warehouse 🔒 readonly → `stock.warehouse`
- `storage_category_id` **(many2one)** — Storage Category → `stock.storage.category`
- `outgoing_move_line_ids` **(one2many)** — Outgoing Move Line → `stock.move.line`
- `incoming_move_line_ids` **(one2many)** — Incoming Move Line → `stock.move.line`
- `valuation_account_id` **(many2one)** — Stock Valuation Account → `account.account`
  > Expense account used to re-qualify products removed from stock and sent to this location
- `subcontractor_ids` **(one2many)** — Subcontractor → `res.partner`

## Campos Calculados (readonly)

- `net_weight` **(float)** — Net Weight 🔒 readonly
- `forecast_weight` **(float)** — Forecasted Weight 🔒 readonly
- `is_empty` **(boolean)** — Is Empty 🔒 readonly
- `is_valued_internal` **(boolean)** — Is valued inside the company 🔒 readonly
- `is_valued_external` **(boolean)** — Is valued outside the company 🔒 readonly
- `barcode_img` **(binary)** — Barcode Img 🔒 readonly
