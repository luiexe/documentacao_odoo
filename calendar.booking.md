# Meeting Booking — `calendar.booking`

**Ordenação padrão:** `start desc, id desc`

---

## Campos Obrigatórios

- `appointment_type_id` **(many2one)** — Appointment Type ⚠️ obrigatório → `appointment.type`
- `start` **(datetime)** — Start ⚠️ obrigatório
- `stop` **(datetime)** — Stop ⚠️ obrigatório
- `product_id` **(many2one)** — Product ⚠️ obrigatório → `product.product`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(html)** — Description
- `name` **(char)** — Customer Name
- `allday` **(boolean)** — Allday
- `asked_capacity` **(integer)** — Asked Capacity
- `booking_token` **(char)** — Access Token 🔒 readonly
- `not_available` **(boolean)** — Is Not Available
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `appointment_answer_input_ids` **(one2many)** — Appointment Answers → `appointment.answer.input`
- `appointment_invite_id` **(many2one)** — Appointment Invite → `appointment.invite`
- `guest_ids` **(many2many)** — Guests → `res.partner`
- `partner_id` **(many2one)** — Contact → `res.partner`
- `booking_line_ids` **(one2many)** — Booking Lines → `calendar.booking.line`
- `staff_user_id` **(many2one)** — Operator → `res.users`
- `account_move_id` **(many2one)** — Appointment Invoice 🔒 readonly → `account.move`
- `calendar_event_id` **(many2one)** — Meeting → `calendar.event`
- `order_line_id` **(many2one)** — Sale Order Line → `sale.order.line`

## Campos Calculados (readonly)

- `duration` **(float)** — Duration 🔒 readonly
