# Barcode Nomenclature — `barcode.nomenclature`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Barcode Nomenclature ⚠️ obrigatório
  > An internal identification of the barcode nomenclature
- `upc_ean_conv` **(selection)** — UPC/EAN Conversion ⚠️ obrigatório
  > UPC Codes can be converted to EAN by prefixing them with a zero. This setting determines if a UPC/EAN barcode should be automatically converted in one way or another when trying to match a rule with the other encoding.
  > Opções: `none` (Never), `ean2upc` (EAN-13 to UPC-A), `upc2ean` (UPC-A to EAN-13), `always` (Always)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `is_gs1_nomenclature` **(boolean)** — Is GS1 Nomenclature
  > This Nomenclature use the GS1 specification, only GS1-128 encoding rules is accepted is this kind of nomenclature.
- `gs1_separator_fnc1` **(char)** — FNC1 Separator
  > Alternative regex delimiter for the FNC1. The separator must not match the begin/end of any related rules pattern.

## Relacionamentos

- `rule_ids` **(one2many)** — Rules → `barcode.rule`
  > The list of barcode rules
