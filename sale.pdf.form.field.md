# Form fields of inside quotation documents. — `sale.pdf.form.field`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `name` **(char)** — Form Field Name ⚠️ obrigatório 🔒 readonly
  > The form field name as written in the PDF.
- `document_type` **(selection)** — Document Type ⚠️ obrigatório 🔒 readonly
  > Opções: `quotation_document` (Header/Footer), `product_document` (Product Document)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `path` **(char)** — Path
  > The path to follow to dynamically fill the form field.  Leave empty to be able to customized it in the quotation form.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `product_document_ids` **(many2many)** — Product Documents → `product.document`
- `quotation_document_ids` **(many2many)** — Quotation Documents → `quotation.document`
