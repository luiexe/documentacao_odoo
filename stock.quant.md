# Quants — `stock.quant`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`
- `location_id` **(many2one)** — Location ⚠️ obrigatório → `stock.location`
- `reserved_quantity` **(float)** — Reserved Quantity ⚠️ obrigatório 🔒 readonly
  > Quantity of reserved products in this quant, in the default unit of measure of the product
- `in_date` **(datetime)** — Incoming Date ⚠️ obrigatório 🔒 readonly

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `quantity` **(float)** — Quantity 🔒 readonly
  > Quantity of products in this quant, in the default unit of measure of the product
- `on_hand` **(boolean)** — On Hand
- `inventory_quantity` **(float)** — Counted
  > The product's counted quantity.
- `inventory_quantity_auto_apply` **(float)** — Inventoried Quantity
- `inventory_diff_quantity` **(float)** — Difference 🔒 readonly
  > Indicates the gap between the product's theoretical quantity and its counted quantity.
- `inventory_date` **(date)** — Scheduled
  > Next date the On Hand Quantity should be counted.
- `inventory_quantity_set` **(boolean)** — Inventory Quantity Set
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `accounting_date` **(date)** — Accounting Date
  > Date at which the accounting entries will be created in case of automated inventory valuation. If empty, the inventory date will be used.
- `dummy_id` **(char)** — Dummy
- `is_subcontract` **(boolean)** — Is Subcontract

## Relacionamentos

- `product_tmpl_id` **(many2one)** — Product Template 🔒 readonly → `product.template`
- `product_uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
  > Default unit of measure used for all stock operations.
- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
  > Let this field empty if this location is shared between companies
- `warehouse_id` **(many2one)** — Warehouse 🔒 readonly → `stock.warehouse`
- `storage_category_id` **(many2one)** — Storage Category 🔒 readonly → `stock.storage.category`
- `lot_id` **(many2one)** — Lot/Serial Number → `stock.lot`
- `package_id` **(many2one)** — Package → `stock.package`
  > The package containing this quant
- `owner_id` **(many2one)** — Owner → `res.partner`
  > This is the owner of the quant
- `product_categ_id` **(many2one)** — Product Category 🔒 readonly → `product.category`
- `user_id` **(many2one)** — Assigned To → `res.users`
  > User assigned to do product count.
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`

## Campos Calculados (readonly)

- `is_favorite` **(boolean)** — Favorite 🔒 readonly
- `cyclic_inventory_frequency` **(integer)** — Inventory Frequency 🔒 readonly
  >  When different than 0, inventory count date for products stored at this location will be automatically set at the defined frequency.
- `lot_properties` **(properties)** — Properties 🔒 readonly
- `sn_duplicated` **(boolean)** — Duplicated Serial Number 🔒 readonly
  > If the same SN is in another Quant
- `available_quantity` **(float)** — Available Quantity 🔒 readonly
  > On hand quantity which hasn't been reserved on a transfer, in the default unit of measure of the product
- `tracking` **(selection)** — Tracking 🔒 readonly
  > Ensure the traceability of a storable product in your warehouse.
  > Opções: `serial` (By Unique Serial Number), `lot` (By Lots), `none` (By Quantity)
- `last_count_date` **(date)** — Last Count Date 🔒 readonly
  > Last time the Quantity was Updated
- `is_outdated` **(boolean)** — Quantity has been moved since last count 🔒 readonly
- `value` **(monetary)** — Value 🔒 readonly
- `cost_method` **(selection)** — Cost Method 🔒 readonly
  > Opções: `standard` (Standard Price), `fifo` (First In First Out (FIFO)), `average` (Average Cost (AVCO))
- `image_1920` **(binary)** — Image 🔒 readonly
- `product_reference_code` **(char)** — Product Reference Code 🔒 readonly
