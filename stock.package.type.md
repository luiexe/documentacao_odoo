# Stock package type — `stock.package.type`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Package Type ⚠️ obrigatório
- `package_use` **(selection)** — Package Use ⚠️ obrigatório
  > Reusable boxes are used for batch picking and emptied afterwards to be reused. In the barcode application, scanning a reusable box will add the products in this box.         Disposable boxes aren't reused, when scanning a disposable box in the barcode application, the contained products are added to the transfer.
  > Opções: `disposable` (Disposable Box), `reusable` (Reusable Box (totes))

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
  > The first in the sequence is the default one.
- `sequence_code` **(char)** — Sequence Prefix
- `height` **(float)** — Height
  > Packaging Height
- `width` **(float)** — Width
  > Packaging Width
- `packaging_length` **(float)** — Length
  > Packaging Length
- `base_weight` **(float)** — Weight
  > Weight of the package type
- `max_weight` **(float)** — Max Weight
  > Maximum weight shippable in this packaging
- `barcode` **(char)** — Barcode
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `shipper_package_code` **(char)** — Carrier Code
- `package_carrier_type` **(selection)** — Carrier
  > Opções: `none` (No carrier integration), `envia` (Envia)
- `envia_mail_type` **(selection)** — Envia Package Type
  > Select the package type for the shipment
  > Opções: `pallet` (Pallet), `box` (Box), `envelope` (Envelope)
- `l10n_br_brand` **(char)** — Brand
  > Brazil: brand of the packaging.

## Relacionamentos

- `sequence_id` **(many2one)** — Reference Sequence → `ir.sequence`
- `company_id` **(many2one)** — Company → `res.company`
- `storage_category_capacity_ids` **(one2many)** — Storage Category Capacity → `stock.storage.category.capacity`
- `route_ids` **(many2many)** — Routes → `stock.route`

## Campos Calculados (readonly)

- `weight_uom_name` **(char)** — Weight unit of measure label 🔒 readonly
- `length_uom_name` **(char)** — Length unit of measure label 🔒 readonly
- `has_quants` **(boolean)** — Has Contents 🔒 readonly
