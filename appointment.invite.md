# Appointment Invite — `appointment.invite`

**Ordenação padrão:** `create_date DESC, id DESC`

---

## Campos Obrigatórios

- `access_token` **(char)** — Token ⚠️ obrigatório 🔒 readonly
- `short_code` **(char)** — Short Code ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `website_published` **(boolean)** — Visible on current website
- `is_published` **(boolean)** — Is Published
- `appointment_type_count` **(integer)** — Selected Appointments Count 🔒 readonly
- `resources_choice` **(selection)** — Assign to
  > Opções: `current_user` (Me), `all_assigned_resources` (Any User), `specific_resources` (Specific Users)
- `resources_resource_choice` **(selection)** — Resources Resource Choice
  > Opções: `all_assigned_resources` (Any Resource), `specific_resources` (Specific Resources)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `website_id` **(many2one)** — Website → `website`
  > Restrict to a specific website.
- `identical_config_id` **(many2one)** — Identical Config → `appointment.invite`
  > Interface field to try to prevent creating identical links
- `appointment_type_ids` **(many2many)** — Appointment Types → `appointment.type`
- `suggested_resource_ids` **(many2many)** — Possible resources 🔒 readonly → `appointment.resource`
- `suggested_staff_user_ids` **(many2many)** — Possible users 🔒 readonly → `res.users`
  > Get the users linked to the appointment type selected to apply a domain on the users that can be selected
- `resource_ids` **(many2many)** — Resources → `appointment.resource`
- `staff_user_ids` **(many2many)** — Users → `res.users`
- `calendar_event_ids` **(one2many)** — Booked Appointments 🔒 readonly → `calendar.event`
- `opportunity_id` **(many2one)** — Opportunity/Lead → `crm.lead`
  > Link an opportunity/lead to the appointment invite created. Used when creating an invitation from the Meeting action in the crm form view.

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
- `short_code_format_warning` **(boolean)** — Short Code Format Warning 🔒 readonly
- `short_code_unique_warning` **(boolean)** — Short Code Unique Warning 🔒 readonly
- `disable_save_button` **(boolean)** — Computes if alert is present 🔒 readonly
- `base_book_url` **(char)** — Base Link URL 🔒 readonly
- `book_url` **(char)** — Link URL 🔒 readonly
- `book_url_params` **(char)** — Link URL params 🔒 readonly
- `redirect_url` **(char)** — Redirect URL 🔒 readonly
- `appointment_type_info_msg` **(html)** — No User Assigned Message 🔒 readonly
- `schedule_based_on` **(char)** — Schedule Based On 🔒 readonly
- `suggested_resource_count` **(integer)** — # Resources 🔒 readonly
- `suggested_staff_user_count` **(integer)** — # Staff Users 🔒 readonly
- `calendar_event_count` **(integer)** — # Bookings 🔒 readonly
- `appointment_type_warning_msg` **(char)** — Different Website Message 🔒 readonly
