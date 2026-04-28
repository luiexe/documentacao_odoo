# NCM Code — `l10n_br.ncm.code`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `code` **(char)** — Code ⚠️ obrigatório
- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `ex` **(char)** — EX
  > Brazil: Use this field to indicate an 'EX Citation' which identifies exceptions to Avalara’s standard fiscal rules. EX Citations help define specific tax treatments (e.g., CST, ST, rate reductions, special benefits) for products with tax behavior different from Avalara’s default settings.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `legal_reference` **(char)** — Legal Reference
  > Brazil: Official technical name required for some NCM codes with specific tax rules (e.g. beverages, electronics).

## Relacionamentos

- `l10n_br_cnae_code_id` **(many2one)** — CNAE Code → `l10n_br.cnae.code`
  > Brazil: Use this field to indicate the CNAE code related to the service being provided. This field is used in municipalities that require CNAE identification per service to validate the NFS-e.
