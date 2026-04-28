# Fetch product images from Barcode Lookup based on the product's barcode. — `product.fetch.image.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `nb_products_selected` **(integer)** — Number of selected products 🔒 readonly
- `nb_products_to_process` **(integer)** — Number of products to process 🔒 readonly
- `nb_products_unable_to_process` **(integer)** — Number of product unprocessable 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `products_to_process` **(many2many)** — Products To Process → `product.product`
  > The list of selected products that meet the criteria (have a barcode and no image)
