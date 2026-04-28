# Manufacturing Report — `mrp.report`

**Ordenação padrão:** `date_finished desc`

---

## Campos Obrigatórios

- `currency_id` **(many2one)** — Currency ⚠️ obrigatório 🔒 readonly → `res.currency`

## Campos Principais

- `id` **(integer)** — Id 🔒 readonly
- `date_finished` **(datetime)** — End Date 🔒 readonly
- `total_cost` **(monetary)** — Total Cost 🔒 readonly
  > Total cost of manufacturing order (component + operation costs + subcontracting cost)
- `component_cost` **(monetary)** — Total Component Cost 🔒 readonly
  > Total cost of components for manufacturing order
- `operation_cost` **(monetary)** — Total Operation Cost 🔒 readonly
  > Total cost of operations for manufacturing order
- `duration` **(float)** — Total Duration of Operations 🔒 readonly
  > Total duration (minutes) of operations for manufacturing order
- `qty_produced` **(float)** — Quantity Produced 🔒 readonly
  > Total quantity produced in product's UoM
- `qty_demanded` **(float)** — Quantity Demanded 🔒 readonly
  > Total quantity demanded in product's UoM
- `yield_rate` **(float)** — Yield Percentage(%) 🔒 readonly
  > Ratio of quantity produced over quantity demanded
- `unit_cost` **(monetary)** — Cost / Unit 🔒 readonly
  > Cost per unit produced (in product UoM) of manufacturing order
- `unit_component_cost` **(monetary)** — Component Cost / Unit 🔒 readonly
  > Component cost per unit produced (in product UoM) of manufacturing order
- `unit_operation_cost` **(monetary)** — Total Operation Cost / Unit 🔒 readonly
  > Operation cost per unit produced (in product UoM) of manufacturing order
- `unit_duration` **(float)** — Duration of Operations / Unit 🔒 readonly
  > Operation duration (minutes) per unit produced of manufacturing order
- `expected_component_cost_unit` **(monetary)** — Expected Component Cost / Unit 🔒 readonly
- `expected_employee_cost_unit` **(monetary)** — Expected Employee Cost / Unit 🔒 readonly
- `expected_operation_cost_unit` **(monetary)** — Expected Operation Cost / Unit 🔒 readonly
- `expected_total_cost_unit` **(monetary)** — Expected Total Cost / Unit 🔒 readonly
- `subcontracting_cost` **(monetary)** — Total Subcontracting Cost 🔒 readonly
  > Total cost of subcontracting for manufacturing order
- `unit_subcontracting_cost` **(monetary)** — Total Subcontracting Cost / Unit 🔒 readonly
  > Subcontracting cost per unit produced (in product UoM) of manufacturing order
- `employee_cost` **(monetary)** — Total Employee Cost 🔒 readonly
  > Total cost of employees for manufacturing order
- `unit_employee_cost` **(monetary)** — Average Employee Cost / Unit 🔒 readonly
  > Employee Cost per unit produced (in product UoM) of manufacturing order

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `production_id` **(many2one)** — Manufacturing Order 🔒 readonly → `mrp.production`
- `product_id` **(many2one)** — Product 🔒 readonly → `product.product`
