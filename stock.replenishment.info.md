# Stock supplier replenishment information — `stock.replenishment.info`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `product_min_qty` **(float)** — Min ⚠️ obrigatório
  > The minimum Stock level that will trigger a replenishment.
- `product_max_qty` **(float)** — Max ⚠️ obrigatório
  > Stock level to reach when replenishing.
- `based_on` **(selection)** — Based on ⚠️ obrigatório
  > Estimate the sales volume for the period based on past period or order the forecasted quantity for that period.
  > Opções: `one_week` (Last 7 days), `one_month` (Last 30 days), `three_months` (Last 3 months), `one_year` (Last 12 months), `last_year` (Same month last year), `last_year_2` (Next month last year), `last_year_3` (After next month last year), `last_year_quarter` (Last year quarter)
- `percent_factor` **(integer)** — Percent Factor ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `orderpoint_id` **(many2one)** — Orderpoint → `stock.warehouse.orderpoint`
- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
- `warehouseinfo_ids` **(one2many)** — Resupply Routes 🔒 readonly → `stock.route`
  > Routes will be created for these resupply warehouses and you can select them on products and product categories
- `wh_replenishment_option_ids` **(one2many)** — Wh Replenishment Option 🔒 readonly → `stock.replenishment.option`
- `bom_id` **(many2one)** — Bill of Materials 🔒 readonly → `mrp.bom`
- `bom_ids` **(many2many)** — Bom 🔒 readonly → `mrp.bom`
- `supplierinfo_id` **(many2one)** — Vendor Pricelist 🔒 readonly → `product.supplierinfo`
- `supplierinfo_ids` **(many2many)** — Supplierinfo 🔒 readonly → `product.supplierinfo`

## Campos Calculados (readonly)

- `product_uom_name` **(char)** — Product unit of measure label 🔒 readonly
- `qty_to_order` **(float)** — To Order 🔒 readonly
- `json_lead_days` **(char)** — Json Lead Days 🔒 readonly
- `json_replenishment_graph` **(char)** — Json Replenishment Graph 🔒 readonly
- `show_bom_tab` **(boolean)** — Show Bom Tab 🔒 readonly
- `show_vendor_tab` **(boolean)** — Show Vendor Tab 🔒 readonly
