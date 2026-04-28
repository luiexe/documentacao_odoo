# Meeting User/Resource Booking — `calendar.booking.line`

**Ordenação padrão:** `create_date DESC, id DESC`

---

## Campos Obrigatórios

- `calendar_booking_id` **(many2one)** — Meeting Booking ⚠️ obrigatório → `calendar.booking`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `capacity_reserved` **(integer)** — Capacity Reserved 🔒 readonly
- `capacity_used` **(integer)** — Capacity Used 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `appointment_resource_id` **(many2one)** — Resource 🔒 readonly → `appointment.resource`
- `appointment_user_id` **(many2one)** — Users 🔒 readonly → `res.users`
