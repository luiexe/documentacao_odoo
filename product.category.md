# Product Category — `product.category`

**Ordenação padrão:** `complete_name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `complete_name` **(char)** — Complete Name 🔒 readonly
- `parent_path` **(char)** — Parent Path
- `product_properties_definition` **(properties_definition)** — Product Properties
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `packaging_reserve_method` **(selection)** — Reserve Packagings
  > Reserve Only Full Packagings: will not reserve partial packagings. If customer orders 2 pallets of 1000 units each and you only have 1600 in stock, then only 1000 will be reserved Reserve Partial Packagings: allow reserving partial packagings. If customer orders 2 pallets of 1000 units each and you only have 1600 in stock, then 1600 will be reserved
  > Opções: `full` (Reserve Only Full Packagings), `partial` (Reserve Partial Packagings)
- `filter_for_stock_putaway_rule` **(boolean)** — stock.putaway.rule
- `property_valuation` **(selection)** — Inventory Valuation
  > Periodic: The accounting entries are suggested manually in the inventory valuation report.         Perpetual: An accounting entry is automatically created to value the inventory when a product is billed or invoiced.         
  > Opções: `periodic` (Periodic (at closing)), `real_time` (Perpetual (at invoicing))
- `property_cost_method` **(selection)** — Costing Method
  > Standard Price: The products are valued at their standard cost defined on the product.         Average Cost (AVCO): The products are valued at weighted average cost.         First In First Out (FIFO): The products are valued supposing those that enter the company first will also leave it first.         
  > Opções: `standard` (Standard Price), `fifo` (First In First Out (FIFO)), `average` (Average Cost (AVCO))

## Relacionamentos

- `parent_id` **(many2one)** — Parent Category → `product.category`
- `child_id` **(one2many)** — Child Categories → `product.category`
- `property_account_income_categ_id` **(many2one)** — Income Account → `account.account`
  > This account will be used when validating a customer invoice.
- `property_account_expense_categ_id` **(many2one)** — Expense Account → `account.account`
  > The expense is accounted for when a vendor bill is validated, except in anglo-saxon accounting with perpetual inventory valuation in which case the expense (Cost of Goods Sold account) is recognized at the customer invoice validation.
- `route_ids` **(many2many)** — Routes → `stock.route`
- `removal_strategy_id` **(many2one)** — Force Removal Strategy → `product.removal`
  > Set a specific removal strategy that will be used regardless of the source location for this product category.  FIFO: products/lots that were stocked first will be moved out first. LIFO: products/lots that were stocked last will be moved out first. Closest location: products/lots closest to the target location will be moved out first. FEFO: products/lots with the closest removal date will be moved out first (the availability of this method depends on the "Expiration Dates" setting). Least Packages: FIFO but with the least number of packages possible when there are several packages containing the same product.
- `parent_route_ids` **(many2many)** — Parent Routes 🔒 readonly → `stock.route`
- `total_route_ids` **(many2many)** — Total routes 🔒 readonly → `stock.route`
- `putaway_rule_ids` **(one2many)** — Putaway Rules → `stock.putaway.rule`
- `property_stock_journal` **(many2one)** — Stock Journal → `account.journal`
  > When doing automated inventory valuation, this is the Accounting Journal in which entries will be automatically posted when stock moves are processed.
- `property_stock_valuation_account_id` **(many2one)** — Stock Valuation Account → `account.account`
  > When automated inventory valuation is enabled on a product, this account will hold the current value of the products.
- `property_price_difference_account_id` **(many2one)** — Price Difference Account → `account.account`
  > With perpetual valuation, this account will hold the price difference between the standard price and the bill price.
- `account_stock_variation_id` **(many2one)** — Stock Variation Account → `account.account`
  > At closing, register the inventory variation of the period into a specific account
- `property_stock_account_production_cost_id` **(many2one)** — Production Account → `account.account`
  > This account will be used as a valuation counterpart for both components and final products for manufacturing orders.                 If there are any workcenter/employee costs, this value will remain on the account once the production is completed.

## Campos Calculados (readonly)

- `product_count` **(integer)** — # Products 🔒 readonly
  > The number of products under this category (Does not consider the children categories)
- `anglo_saxon_accounting` **(boolean)** — Use Anglo-Saxon Accounting 🔒 readonly
  > If checked, the product will be valued using the Anglo-Saxon accounting method.
