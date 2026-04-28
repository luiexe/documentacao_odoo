# Mail RTC session — `discuss.channel.rtc.session`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `channel_member_id` **(many2one)** — Channel Member ⚠️ obrigatório → `discuss.channel.member`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `write_date` **(datetime)** — Last Updated On
- `is_screen_sharing_on` **(boolean)** — Is sharing the screen
- `is_camera_on` **(boolean)** — Is sending user video
- `is_muted` **(boolean)** — Is microphone muted
- `is_deaf` **(boolean)** — Has disabled incoming sound
- `create_date` **(datetime)** — Created on 🔒 readonly

## Relacionamentos

- `channel_id` **(many2one)** — Channel 🔒 readonly → `discuss.channel`
- `partner_id` **(many2one)** — Partner 🔒 readonly → `res.partner`
- `guest_id` **(many2one)** — Guest 🔒 readonly → `mail.guest`
