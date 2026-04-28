# Stock Rule — `stock.rule`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
  > This field will fill the packing origin and the name of its moves
- `action` **(selection)** — Action ⚠️ obrigatório
  > Opções: `pull` (Pull From), `push` (Push To), `pull_push` (Pull & Push), `manufacture` (Manufacture), `buy` (Buy)
- `location_dest_id` **(many2one)** — Destination Location ⚠️ obrigatório → `stock.location`
- `route_id` **(many2one)** — Route ⚠️ obrigatório → `stock.route`
- `procure_method` **(selection)** — Supply Method ⚠️ obrigatório
  > Take From Stock: the products will be taken from the available stock of the source location. Trigger Another Rule: the system will try to find a stock rule to bring the products in the source location. The available stock will be ignored. Take From Stock, if Unavailable, Trigger Another Rule: the products will be taken from the available stock of the source location.If there is no stock available, the system will try to find a  rule to bring the products in the source location.
  > Opções: `make_to_stock` (Take From Stock), `make_to_order` (Trigger Another Rule), `mts_else_mto` (Take From Stock, if unavailable, Trigger Another Rule)
- `picking_type_id` **(many2one)** — Operation Type ⚠️ obrigatório → `stock.picking.type`
- `auto` **(selection)** — Automatic Move ⚠️ obrigatório
  > The 'Manual Operation' value will create a stock move after the current one. With 'Automatic No Step Added', the location is replaced in the original move.
  > Opções: `manual` (Manual Operation), `transparent` (Automatic No Step Added)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
  > If unchecked, it will allow you to hide the rule without removing it.
- `sequence` **(integer)** — Sequence
- `location_dest_from_rule` **(boolean)** — Destination location origin from rule
  > When set to True the destination location of the stock.move will be the rule.Otherwise, it takes it from the picking type.
- `route_sequence` **(integer)** — Route Sequence 🔒 readonly
- `delay` **(integer)** — Lead Time
  > The expected date of the created transfer will be computed based on this lead time.
- `propagate_cancel` **(boolean)** — Cancel Next Move
  > When ticked, if the move created by this rule is cancelled, the next move will be cancelled too.
- `propagate_carrier` **(boolean)** — Propagation of carrier
  > When ticked, carrier of shipment will be propagated.
- `push_domain` **(char)** — Push Applicability
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `location_src_id` **(many2one)** — Source Location → `stock.location`
- `route_company_id` **(many2one)** — Route Company 🔒 readonly → `res.company`
  > Leave this field empty if this route is shared between all companies
- `partner_address_id` **(many2one)** — Partner Address → `res.partner`
  > Address where goods should be delivered. Optional.
- `warehouse_id` **(many2one)** — Warehouse → `stock.warehouse`

## Campos Calculados (readonly)

- `picking_type_code_domain` **(json)** — Picking Type Code Domain 🔒 readonly
- `rule_message` **(html)** — Rule Message 🔒 readonly
