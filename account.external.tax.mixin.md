# Mixin to manage common parts of external tax calculation — `account.external.tax.mixin`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `l10n_br_use_type` **(selection)** — Purpose of Use
  > Brazil: this will override the purpose of use for all products sold here.
  > Opções: `use or consumption` (Use or consumption), `resale` (Resale), `agricultural production` (Agricultural production), `production` (Production), `fixed assets` (Fixed assets), `notApplicable` (Not applicable)
- `l10n_br_presence` **(selection)** — Presence
  > Brazil: Defines if the buyer was physically present during the transaction, affecting tax calculation and location.
  > Opções: `0` (Not applicable), `1` (Present), `2` (Remote, internet), `3` (Remote, phone), `4` (NFC-e home delivery), `5` (In-person operation, for establishment (v3)), `9` (Remote, others)

## Relacionamentos

- `l10n_br_cnae_code_id` **(many2one)** — CNAE Code → `l10n_br.cnae.code`
  > Brazil: the company's CNAE code for tax calculation and EDI.
- `l10n_br_goods_operation_type_id` **(many2one)** — Goods Operation Type → `l10n_br.operation.type`
  > Brazil: this is the operation type related to the goods transaction. This will be used as a default on transaction lines.

## Campos Calculados (readonly)

- `is_tax_computed_externally` **(boolean)** — Is Tax Computed Externally 🔒 readonly
  > Technical field to determine if tax is calculated using an external service instead of Odoo.
- `l10n_br_is_service_transaction` **(boolean)** — Is Service Transaction 🔒 readonly
  > Technical field used to determine if this transaction should be sent to the service or goods API.
- `l10n_br_is_avatax` **(boolean)** — Is Brazilian Avatax 🔒 readonly
  > Technical field used to check if this record requires tax calculation or EDI via Avatax.
- `l10n_br_avatax_warnings` **(json)** — L10N Br Avatax Warnings 🔒 readonly
