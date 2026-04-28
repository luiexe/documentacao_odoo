# Channel / Partners (Members) — `slide.channel.partner`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `channel_id` **(many2one)** — Course ⚠️ obrigatório → `slide.channel`
- `member_status` **(selection)** — Attendee Status ⚠️ obrigatório 🔒 readonly
  > Opções: `invited` (Invite Sent), `joined` (Joined), `ongoing` (Ongoing), `completed` (Finished)
- `partner_id` **(many2one)** — Partner ⚠️ obrigatório → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `completion` **(integer)** — % Completed Contents
- `completed_slides_count` **(integer)** — # Completed Contents
- `last_invitation_date` **(datetime)** — Last Invitation Date
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `survey_certification_success` **(boolean)** — Certified

## Relacionamentos

- `channel_user_id` **(many2one)** — Responsible 🔒 readonly → `res.users`
- `channel_website_id` **(many2one)** — Website 🔒 readonly → `website`
  > Restrict to a specific website.
- `next_slide_id` **(many2one)** — Next Lesson 🔒 readonly → `slide.slide`

## Campos Calculados (readonly)

- `partner_email` **(char)** — Email 🔒 readonly
- `channel_type` **(selection)** — Course type 🔒 readonly
  > Defines the course type (e.g., "Training" for interactive learning, or "Documentation" for resources and guides).
  > Opções: `training` (Training), `documentation` (Documentation)
- `channel_visibility` **(selection)** — Show Course To 🔒 readonly
  > Defines who can access your courses and their content.
  > Opções: `public` (Everyone), `connected` (Signed In), `members` (Course Attendees), `link` (Anyone with the link)
- `channel_enroll` **(selection)** — Enroll Policy 🔒 readonly
  > Defines how people can enroll to your Course.
  > Opções: `public` (Open), `invite` (On Invitation)
- `invitation_link` **(char)** — Invitation Link 🔒 readonly
- `nbr_certification` **(integer)** — Number of Certifications 🔒 readonly
