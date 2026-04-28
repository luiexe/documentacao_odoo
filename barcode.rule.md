# Barcode Rule — `barcode.rule`

**Ordenação padrão:** `sequence asc, id`

---

## Campos Obrigatórios

- `name` **(char)** — Rule Name ⚠️ obrigatório
  > An internal identification for this barcode nomenclature rule
- `encoding` **(selection)** — Encoding ⚠️ obrigatório
  > This rule will apply only if the barcode is encoded with the specified encoding
  > Opções: `any` (Any), `ean13` (EAN-13), `ean8` (EAN-8), `upca` (UPC-A), `gs1-128` (GS1-128)
- `type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `alias` (Alias), `product` (Unit Product), `quantity` (Quantity), `weight` (Weighted Product), `location` (Location), `location_dest` (Destination location), `lot` (Lot), `package` (Package), `use_date` (Best before Date), `expiration_date` (Expiration Date), `package_type` (Package Type), `pack_date` (Pack Date)
- `pattern` **(char)** — Barcode Pattern ⚠️ obrigatório
  > The barcode matching pattern
- `alias` **(char)** — Alias ⚠️ obrigatório
  > The matched pattern will alias to this barcode

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
  > Used to order rules such that rules with a smaller sequence match first
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `gs1_content_type` **(selection)** — GS1 Content Type
  > The GS1 content type defines what kind of data the rule will process the barcode as:        * Date: the barcode will be converted into a Odoo datetime;        * Measure: the barcode's value is related to a specific unit;        * Numeric Identifier: fixed length barcode following a specific encoding;        * Alpha-Numeric Name: variable length barcode.
  > Opções: `date` (Date), `measure` (Measure), `identifier` (Numeric Identifier), `alpha` (Alpha-Numeric Name)
- `gs1_decimal_usage` **(boolean)** — Decimal
  > If True, use the last digit of AI to determine where the first decimal is

## Relacionamentos

- `barcode_nomenclature_id` **(many2one)** — Barcode Nomenclature → `barcode.nomenclature`
- `associated_uom_id` **(many2one)** — Associated Uom → `uom.uom`

## Campos Calculados (readonly)

- `is_gs1_nomenclature` **(boolean)** — Is GS1 Nomenclature 🔒 readonly
  > This Nomenclature use the GS1 specification, only GS1-128 encoding rules is accepted is this kind of nomenclature.
