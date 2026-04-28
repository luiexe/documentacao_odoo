# Choose from the available Envia.com shipping methods — `envia.shipping.wizard`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `available_services` **(json)** — Available Services
  > Contains the list of available services for the Envia.com account to select from.
- `selected_service_code` **(char)** — Selected Service
- `selected_carrier_code` **(char)** — Selected Carrier
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `carrier_id` **(many2one)** — Delivery → `delivery.carrier`
