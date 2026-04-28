# Appointment Booking Line — `appointment.booking.line`

**Ordenação padrão:** `event_start desc, id desc`

---

## Campos Obrigatórios

- `capacity_reserved` **(integer)** — Capacity Reserved ⚠️ obrigatório
  > Capacity reserved by the user
- `calendar_event_id` **(many2one)** — Booking ⚠️ obrigatório → `calendar.event`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `capacity_used` **(integer)** — Capacity Used 🔒 readonly
  > Capacity that will be used based on the capacity and user/resource selected
- `event_start` **(datetime)** — Booking Start 🔒 readonly
  > Start date of an event, without time for full days events
- `event_stop` **(datetime)** — Booking End 🔒 readonly
  > Stop date of an event, without time for full days events
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `appointment_resource_id` **(many2one)** — Appointment Resource → `appointment.resource`
- `appointment_user_id` **(many2one)** — Appointment User → `res.users`
- `appointment_type_id` **(many2one)** — Appointment 🔒 readonly → `appointment.type`

## Campos Calculados (readonly)

- `active` **(boolean)** — Active 🔒 readonly
  > If the active field is set to false, it will allow you to hide the event alarm information without removing it.
