# Channel Member — `discuss.channel.member`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `channel_id` **(many2one)** — Channel ⚠️ obrigatório → `discuss.channel`
- `new_message_separator` **(integer)** — New Message Separator ⚠️ obrigatório
  > Message id before which the separator should be displayed

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `custom_channel_name` **(char)** — Custom channel name
- `custom_notifications` **(selection)** — Customized Notifications
  > Use default from user settings if not specified. This setting will only be applied to channels.
  > Opções: `all` (All Messages), `mentions` (Mentions Only), `no_notif` (Nothing)
- `mute_until_dt` **(datetime)** — Mute notifications until
  > If set, the member will not receive notifications from the channel until this date.
- `unpin_dt` **(datetime)** — Unpin date
  > Contains the date and time when the channel was unpinned by the user.
- `last_interest_dt` **(datetime)** — Last Interest
  > Contains the date and time of the last interesting event that happened in this channel for this user. This includes: creating, joining, pinning
- `last_seen_dt` **(datetime)** — Last seen date
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `partner_id` **(many2one)** — Partner → `res.partner`
- `guest_id` **(many2one)** — Guest → `mail.guest`
- `fetched_message_id` **(many2one)** — Last Fetched → `mail.message`
- `seen_message_id` **(many2one)** — Last Seen → `mail.message`
- `rtc_session_ids` **(one2many)** — RTC Sessions → `discuss.channel.rtc.session`
- `rtc_inviting_session_id` **(many2one)** — Ringing session → `discuss.channel.rtc.session`

## Campos Calculados (readonly)

- `is_self` **(boolean)** — Is Self 🔒 readonly
- `message_unread_counter` **(integer)** — Unread Messages Counter 🔒 readonly
- `is_pinned` **(boolean)** — Is pinned on the interface 🔒 readonly
