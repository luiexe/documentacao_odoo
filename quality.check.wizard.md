# Wizard for Quality Check Pop Up — `quality.check.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `check_ids` **(many2many)** — Check ⚠️ obrigatório → `quality.check`
- `current_check_id` **(many2one)** — Current Check ⚠️ obrigatório → `quality.check`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `qty_failed` **(float)** — Qty Failed
- `qty_tested` **(float)** — Quantity Tested
  > Quantity of product tested within the lot
- `measure` **(float)** — Measure
- `picture` **(binary)** — Picture
- `note` **(html)** — Note
- `additional_note` **(text)** — Additional Note
  > Additional remarks concerning this check.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `failure_location_id` **(many2one)** — Failure Location → `stock.location`
- `potential_failure_location_ids` **(many2many)** — Failure Locations 🔒 readonly → `stock.location`
  > If quality check fails, a destination location is chosen from this list for - each failed specific product quantity if control is per quantity  /- all quantities of a product if control is per product  /- all quantities of products in the operation if control is per operation
- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
- `lot_line_id` **(many2one)** — Lot Line 🔒 readonly → `stock.lot`
- `uom_id` **(many2one)** — Unit 🔒 readonly → `uom.uom`
  > Default unit of measure used for all stock operations.

## Campos Calculados (readonly)

- `nb_checks` **(integer)** — Nb Checks 🔒 readonly
- `position_current_check` **(integer)** — Position Current Check 🔒 readonly
- `is_last_check` **(boolean)** — Is Last Check 🔒 readonly
- `name` **(char)** — Reference 🔒 readonly
- `title` **(char)** — Title 🔒 readonly
- `lot_name` **(char)** — Lot/Serial Number Name 🔒 readonly
- `qty_line` **(float)** — Quantity 🔒 readonly
- `qty_to_test` **(float)** — Quantity to Test 🔒 readonly
  > Quantity of product to test within the lot
- `measure_on` **(selection)** — Control per 🔒 readonly
  > Operation = One quality check is requested at the operation level.                   Product = A quality check is requested per product.                  Quantity = A quality check is requested for each new product quantity registered, with partial quantity checks also possible.
  > Opções: `operation` (Operation), `product` (Product), `move_line` (Quantity)
- `quality_state` **(selection)** — Status 🔒 readonly
  > Opções: `none` (To do), `pass` (Passed), `fail` (Failed)
- `test_type` **(char)** — Technical name 🔒 readonly
- `norm_unit` **(char)** — Norm Unit 🔒 readonly
- `is_lot_tested_fractionally` **(boolean)** — Lot Tested Fractionally 🔒 readonly
  > Determines if only a fraction of the lot should be tested
- `testing_percentage_within_lot` **(float)** — Testing Percentage Within Lot 🔒 readonly
  > Defines the percentage within a lot that should be tested
- `warning_message` **(text)** — Warning Message 🔒 readonly
- `failure_message` **(html)** — Failure Message 🔒 readonly
- `show_lot_text` **(boolean)** — Show Lot Text 🔒 readonly
- `product_tracking` **(selection)** — Tracking 🔒 readonly
  > Ensure the traceability of a storable product in your warehouse.
  > Opções: `serial` (By Unique Serial Number), `lot` (By Lots), `none` (By Quantity)
