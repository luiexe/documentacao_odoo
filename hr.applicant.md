# Applicant — `hr.applicant`

**Ordenação padrão:** `priority desc, sequence, id desc`

---

## Campos Obrigatórios

- `kanban_state` **(selection)** — Kanban State ⚠️ obrigatório
  > Opções: `normal` (In Progress), `done` (Ready for Next Stage), `waiting` (Waiting), `blocked` (Blocked)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `phone_sanitized` **(char)** — Sanitized Number 🔒 readonly
  > Field used to store sanitized phone number. Helps speeding up searches and comparisons.
- `phone_mobile_search` **(char)** — Phone Number
- `email_normalized` **(char)** — Normalized Email 🔒 readonly
  > This field is used to search on email address as the primary email field can contain more than strictly an email address.
- `message_bounce` **(integer)** — Bounce
  > Counter of the number of bounced emails for this contact
- `email_cc` **(char)** — Email cc
- `sequence` **(integer)** — Sequence
- `active` **(boolean)** — Active
  > If the active field is set to false, it will allow you to hide the case without removing it.
- `partner_name` **(char)** — Applicant's Name
- `email_from` **(char)** — Email
- `partner_phone` **(char)** — Phone
- `partner_phone_sanitized` **(char)** — Sanitized Phone Number 🔒 readonly
- `linkedin_profile` **(char)** — LinkedIn Profile
- `availability` **(date)** — Availability
  > The date at which the applicant will be available to start working
- `color` **(integer)** — Color Index
- `employee_name` **(char)** — Employee Name
- `probability` **(float)** — Probability
- `create_date` **(datetime)** — Applied on 🔒 readonly
- `date_closed` **(datetime)** — Hire Date
- `date_open` **(datetime)** — Assigned 🔒 readonly
- `date_last_stage_update` **(datetime)** — Last Stage Update
- `priority` **(selection)** — Evaluation
  > Opções: `0` (Normal), `1` (Good), `2` (Very Good), `3` (Excellent)
- `delay_close` **(float)** — Delay to Close 🔒 readonly
  > Number of days to close
- `applicant_properties` **(properties)** — Properties
- `applicant_notes` **(html)** — Applicant Notes
- `refuse_date` **(datetime)** — Refuse Date
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `interview_invite_code` **(char)** — Interview Invite Code 🔒 readonly
- `extract_state` **(selection)** — Extract state
  > Opções: `no_extract_requested` (No extract requested), `not_enough_credit` (Not enough credits), `error_status` (An error occurred), `waiting_extraction` (Waiting extraction), `extract_not_ready` (waiting extraction, but it is not ready), `waiting_validation` (Waiting validation), `to_validate` (To validate), `done` (Completed flow)
- `extract_status` **(char)** — Extract status
- `extract_document_uuid` **(char)** — ID of the request to IAP-OCR 🔒 readonly
- `is_in_extractable_state` **(boolean)** — Is In Extractable State 🔒 readonly
- `extract_state_processed` **(boolean)** — Extract State Processed 🔒 readonly

## Relacionamentos

- `campaign_id` **(many2one)** — Campaign → `utm.campaign`
  > This is a name that helps you keep track of your different campaign efforts, e.g. Fall_Drive, Christmas_Special
- `source_id` **(many2one)** — Source → `utm.source`
  > This is the source of the link, e.g. Search Engine, another domain, or name of email list
- `medium_id` **(many2one)** — Medium → `utm.medium`
  > This displays how the applicant has reached out, e.g. via Email, LinkedIn, Website, etc.
- `message_main_attachment_id` **(many2one)** — Main Attachment → `ir.attachment`
- `partner_id` **(many2one)** — Contact → `res.partner`
- `type_id` **(many2one)** — Degree → `hr.recruitment.degree`
- `employee_id` **(many2one)** — Employee → `hr.employee`
  > Employee linked to the applicant.
- `stage_id` **(many2one)** — Stage → `hr.recruitment.stage`
- `last_stage_id` **(many2one)** — Last Stage → `hr.recruitment.stage`
  > Stage of the applicant before being in the current stage. Used for lost cases analysis.
- `categ_ids` **(many2many)** — Tags → `hr.applicant.category`
- `company_id` **(many2one)** — Company → `res.company`
- `user_id` **(many2one)** — Recruiter → `res.users`
- `job_id` **(many2one)** — Job Position → `hr.job`
- `department_id` **(many2one)** — Department → `hr.department`
- `attachment_ids` **(one2many)** — Attachments → `ir.attachment`
- `refuse_reason_id` **(many2one)** — Refuse Reason → `hr.applicant.refuse.reason`
- `meeting_ids` **(one2many)** — Meetings → `calendar.event`
- `interviewer_ids` **(many2many)** — Interviewers → `res.users`
- `talent_pool_ids` **(many2many)** — Talent Pools → `hr.talent.pool`
- `pool_applicant_id` **(many2one)** — Pool Applicant → `hr.applicant`
- `applicant_skill_ids` **(one2many)** — Skills → `hr.applicant.skill`
- `current_applicant_skill_ids` **(one2many)** — Current Applicant Skill → `hr.applicant.skill`
- `skill_ids` **(many2many)** — Skill 🔒 readonly → `hr.skill`
- `matching_skill_ids` **(many2many)** — Matching Skills 🔒 readonly → `hr.skill`
- `missing_skill_ids` **(many2many)** — Missing Skills 🔒 readonly → `hr.skill`

## Campos Calculados (readonly)

- `duration_tracking` **(json)** — Status time 🔒 readonly
  > JSON that maps ids from a many2one field to seconds spent
- `rotting_days` **(integer)** — Days Rotting 🔒 readonly
  > Day count since this resource was last updated
- `is_rotting` **(boolean)** — Rotting 🔒 readonly
- `phone_sanitized_blacklisted` **(boolean)** — Phone Blacklisted 🔒 readonly
  > If the sanitized phone number is on the blacklist, the contact won't receive mass mailing sms anymore, from any list
- `phone_blacklisted` **(boolean)** — Blacklisted Phone is Phone 🔒 readonly
  > Indicates if a blacklisted sanitized phone number is a phone number. Helps distinguish which number is blacklisted             when there is both a mobile and phone field in a model.
- `is_blacklisted` **(boolean)** — Blacklist 🔒 readonly
  > If the email address is on the blacklist, the contact won't receive mass mailing anymore, from any list
- `emp_is_active` **(boolean)** — Employee Active 🔒 readonly
  > If the active field is set to False, it will allow you to hide the resource record without removing it.
- `day_open` **(float)** — Days to Open 🔒 readonly
- `day_close` **(float)** — Days to Close 🔒 readonly
- `user_email` **(char)** — User Email 🔒 readonly
- `attachment_number` **(integer)** — Number of Attachments 🔒 readonly
- `legend_blocked` **(char)** — Kanban Blocked 🔒 readonly
- `legend_done` **(char)** — Kanban Valid 🔒 readonly
- `legend_waiting` **(char)** — Kanban Waiting 🔒 readonly
- `legend_normal` **(char)** — Kanban Ongoing 🔒 readonly
- `meeting_display_text` **(char)** — Meeting Display Text 🔒 readonly
- `meeting_display_date` **(date)** — Meeting Display Date 🔒 readonly
- `application_status` **(selection)** — Application Status 🔒 readonly
  > Opções: `ongoing` (Ongoing), `hired` (Hired), `refused` (Refused), `archived` (Archived)
- `application_count` **(integer)** — Application Count 🔒 readonly
  > Applications with the same email or phone or mobile
- `is_pool_applicant` **(boolean)** — Is Pool Applicant 🔒 readonly
- `is_applicant_in_pool` **(boolean)** — Is Applicant In Pool 🔒 readonly
- `talent_pool_count` **(integer)** — Talent Pool Count 🔒 readonly
- `extract_error_message` **(text)** — Error message 🔒 readonly
- `extract_can_show_send_button` **(boolean)** — Can show the ocr send button 🔒 readonly
- `sign_request_count` **(integer)** — # Signatures 🔒 readonly
- `matching_score` **(integer)** — Matching Score 🔒 readonly
