# Appointment: Time Slot — `appointment.slot`

**Ordenação padrão:** `weekday, start_hour, start_datetime, end_datetime`

---

## Campos Obrigatórios

- `slot_type` **(selection)** — Slot type ⚠️ obrigatório 🔒 readonly
  > Defines the type of slot. The regular slot is the default type which is used for         appointment type that are used recurringly in type like medical appointment.         The one shot type is only used when an user create a custom appointment type for a client by         defining non-recurring time slot (e.g. 10th of April 2021 from 10 to 11 am) from its calendar.
  > Opções: `recurring` (Regular), `unique` (One Shot)
- `weekday` **(selection)** — Week Day ⚠️ obrigatório
  > Opções: `1` (Monday), `2` (Tuesday), `3` (Wednesday), `4` (Thursday), `5` (Friday), `6` (Saturday), `7` (Sunday)
- `start_hour` **(float)** — Starting Hour ⚠️ obrigatório
- `end_hour` **(float)** — Ending Hour ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `allday` **(boolean)** — All day
  > Determine if the slot englobe the whole day, mainly used for unique slot type
- `start_datetime` **(datetime)** — From
  > Start datetime for unique slot type management
- `end_datetime` **(datetime)** — To
  > End datetime for unique slot type management
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `appointment_type_id` **(many2one)** — Appointment Type → `appointment.type`
- `restrict_to_user_ids` **(many2many)** — Restrict to Users → `res.users`
  > If empty, all users are considered to be available. If set, only the selected users will be taken into account for this slot.
- `restrict_to_resource_ids` **(many2many)** — Restrict to Resources → `appointment.resource`
  > If empty, all resources are considered to be available. If set, only the selected resources will be taken into account for this slot.

## Campos Calculados (readonly)

- `schedule_based_on` **(selection)** — Book 🔒 readonly
  > Opções: `users` (Users), `resources` (Resources)
- `duration` **(float)** — Duration 🔒 readonly
