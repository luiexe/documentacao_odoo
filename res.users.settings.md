# User Settings — `res.users.settings`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `user_id` **(many2one)** — User ⚠️ obrigatório → `res.users`
- `color_scheme` **(selection)** — Color Scheme ⚠️ obrigatório
  > Opções: `system` (System), `light` (Light), `dark` (Dark)
- `calendar_default_privacy` **(selection)** — Calendar Default Privacy ⚠️ obrigatório
  > Default privacy setting for whom the calendar events will be visible.
  > Opções: `public` (Public), `private` (Private), `confidential` (Only internal users)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `homemenu_config` **(json)** — Home Menu Configuration 🔒 readonly
- `is_discuss_sidebar_category_channel_open` **(boolean)** — Is discuss sidebar category channel open?
- `is_discuss_sidebar_category_chat_open` **(boolean)** — Is discuss sidebar category chat open?
- `push_to_talk_key` **(char)** — Push-To-Talk shortcut
  > String formatted to represent a key with modifiers following this pattern: shift.ctrl.alt.key, e.g: truthy.1.true.b
- `use_push_to_talk` **(boolean)** — Use the push to talk feature
- `voice_active_duration` **(integer)** — Duration of voice activity in ms
  > How long the audio broadcast will remain active after passing the volume threshold
- `channel_notifications` **(selection)** — Channel Notifications
  > This setting will only be applied to channels. Mentions only if not specified.
  > Opções: `all` (All Messages), `no_notif` (Nothing)
- `is_discuss_sidebar_category_whatsapp_open` **(boolean)** — WhatsApp Category Open
  > If checked, the WhatsApp category is open in the discuss sidebar

## Relacionamentos

- `embedded_actions_config_ids` **(one2many)** — Embedded Actions Config → `res.users.settings.embedded.action`
- `volume_settings_ids` **(one2many)** — Volumes of other partners → `res.users.settings.volumes`
