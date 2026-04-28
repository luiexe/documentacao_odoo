# Course — `slide.channel`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `channel_type` **(selection)** — Course type ⚠️ obrigatório
  > Defines the course type (e.g., "Training" for interactive learning, or "Documentation" for resources and guides).
  > Opções: `training` (Training), `documentation` (Documentation)
- `enroll` **(selection)** — Enroll Policy ⚠️ obrigatório
  > Defines how people can enroll to your Course.
  > Opções: `public` (Open), `invite` (On Invitation)
- `visibility` **(selection)** — Show Course To ⚠️ obrigatório
  > Defines who can access your courses and their content.
  > Opções: `public` (Everyone), `connected` (Signed In), `members` (Course Attendees), `link` (Anyone with the link)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `website_published` **(boolean)** — Visible on current website
- `is_published` **(boolean)** — Is Published
- `is_seo_optimized` **(boolean)** — SEO optimized 🔒 readonly
- `website_meta_title` **(char)** — Website meta title
- `website_meta_description` **(text)** — Website meta description
- `website_meta_keywords` **(char)** — Website meta keywords
- `website_meta_og_img` **(char)** — Website opengraph image
- `seo_name` **(char)** — Seo name
- `cover_properties` **(text)** — Cover Properties
- `image_1920` **(binary)** — Image
- `image_1024` **(binary)** — Image 1024 🔒 readonly
- `image_512` **(binary)** — Image 512 🔒 readonly
- `image_256` **(binary)** — Image 256 🔒 readonly
- `image_128` **(binary)** — Image 128 🔒 readonly
- `rating_last_value` **(float)** — Rating Last Value 🔒 readonly
- `active` **(boolean)** — Active
- `description` **(html)** — Description
  > The description that is displayed on top of the course page, just below the title
- `description_short` **(html)** — Short Description
  > The description that is displayed on the course card
- `description_html` **(html)** — Detailed Description
- `sequence` **(integer)** — Sequence
- `color` **(integer)** — Color Index
  > Used to decorate kanban view
- `slide_last_update` **(date)** — Last Update 🔒 readonly
- `promote_strategy` **(selection)** — Featured Content
  > Defines the content that will be promoted on the course home page
  > Opções: `latest` (Latest Created), `most_voted` (Most Voted), `most_viewed` (Most Viewed), `specific` (Select Manually), `none` (None)
- `access_token` **(char)** — Security Token
- `nbr_document` **(integer)** — Documents 🔒 readonly
- `nbr_video` **(integer)** — Videos 🔒 readonly
- `nbr_infographic` **(integer)** — Infographics 🔒 readonly
- `nbr_article` **(integer)** — Articles 🔒 readonly
- `nbr_quiz` **(integer)** — Number of Quizs 🔒 readonly
- `total_slides` **(integer)** — Number of Contents 🔒 readonly
- `total_views` **(integer)** — Visits 🔒 readonly
- `total_votes` **(integer)** — Votes 🔒 readonly
- `total_time` **(float)** — Duration 🔒 readonly
- `allow_comment` **(boolean)** — Allow rating on Course
  > Allow Attendees to like and comment your content and to submit reviews on your course.
- `enroll_msg` **(html)** — Enroll Message
  > Message explaining the enroll process
- `karma_gen_channel_rank` **(integer)** — Course ranked
- `karma_gen_channel_finish` **(integer)** — Course finished
- `karma_review` **(integer)** — Add Review
  > Karma needed to add a review on the course
- `karma_slide_comment` **(integer)** — Add Comment
  > Karma needed to add a comment on a slide of this course
- `karma_slide_vote` **(integer)** — Vote
  > Karma needed to like/dislike a slide of this course.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `nbr_certification` **(integer)** — Number of Certifications 🔒 readonly

## Relacionamentos

- `website_id` **(many2one)** — Website → `website`
  > Restrict to a specific website.
- `user_id` **(many2one)** — Responsible → `res.users`
- `tag_ids` **(many2many)** — Tags → `slide.channel.tag`
  > Used to categorize and filter displayed channels/courses
- `slide_ids` **(one2many)** — Slides and categories → `slide.slide`
- `slide_content_ids` **(one2many)** — Content 🔒 readonly → `slide.slide`
- `slide_category_ids` **(one2many)** — Categories 🔒 readonly → `slide.slide`
- `promoted_slide_id` **(many2one)** — Promoted Slide → `slide.slide`
- `publish_template_id` **(many2one)** — New Content Notification → `mail.template`
  > Defines the email your Attendees will receive each time you upload new content.
- `share_channel_template_id` **(many2one)** — Channel Share Template → `mail.template`
  > Email template used when sharing a channel
- `share_slide_template_id` **(many2one)** — Share Template → `mail.template`
  > Email template used when sharing a slide
- `completed_template_id` **(many2one)** — Completion Notification → `mail.template`
  > Defines the email your Attendees will receive once they reach the end of your course.
- `enroll_group_ids` **(many2many)** — Auto Enroll Groups → `res.groups`
  > Members of those groups are automatically added as members of the channel.
- `upload_group_ids` **(many2many)** — Upload Groups → `res.groups`
  > Group of users allowed to publish contents on a documentation course.
- `partner_ids` **(many2many)** — Attendees 🔒 readonly → `res.partner`
  > Enrolled partners in the course
- `prerequisite_channel_ids` **(many2many)** — Prerequisites → `slide.channel`
  > Prerequisite courses to complete before accessing this one.
- `prerequisite_of_channel_ids` **(many2many)** — Prerequisite Of → `slide.channel`
  > Courses that have this course as prerequisite.
- `helpdesk_team_ids` **(many2many)** — Helpdesk Team → `helpdesk.team`

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
- `rating_last_feedback` **(text)** — Rating Last Feedback 🔒 readonly
- `rating_last_image` **(binary)** — Rating Last Image 🔒 readonly
- `rating_count` **(integer)** — Rating count 🔒 readonly
- `rating_avg` **(float)** — Average Rating 🔒 readonly
- `rating_avg_text` **(selection)** — Rating Avg Text 🔒 readonly
  > Opções: `top` (Happy), `ok` (Neutral), `ko` (Unhappy), `none` (Not Rated yet)
- `rating_percentage_satisfaction` **(float)** — Rating Satisfaction 🔒 readonly
- `rating_last_text` **(selection)** — Rating Text 🔒 readonly
  > Opções: `top` (Happy), `ok` (Neutral), `ko` (Unhappy), `none` (Not Rated yet)
- `rating_avg_stars` **(float)** — Rating Average (Stars) 🔒 readonly
- `website_default_background_image_url` **(char)** — Background image URL 🔒 readonly
- `members_count` **(integer)** — # Enrolled Attendees 🔒 readonly
- `members_all_count` **(integer)** — # Enrolled or Invited Attendees 🔒 readonly
- `members_engaged_count` **(integer)** — # Active Attendees 🔒 readonly
  > Active attendees include both 'joined' and 'ongoing' attendees.
- `members_completed_count` **(integer)** — # Completed Attendees 🔒 readonly
- `members_invited_count` **(integer)** — # Invited Attendees 🔒 readonly
- `completed` **(boolean)** — Done 🔒 readonly
- `completion` **(integer)** — Completion 🔒 readonly
- `can_upload` **(boolean)** — Can Upload 🔒 readonly
- `has_requested_access` **(boolean)** — Access Requested 🔒 readonly
- `is_member` **(boolean)** — Is Enrolled Attendee 🔒 readonly
  > Is the attendee actively enrolled.
- `is_member_invited` **(boolean)** — Is Invited Attendee 🔒 readonly
  > Is the invitation for this attendee pending.
- `is_visible` **(boolean)** — Is Visible On Website 🔒 readonly
- `partner_has_new_content` **(boolean)** — Partner Has New Content 🔒 readonly
- `can_review` **(boolean)** — Can Review 🔒 readonly
- `can_comment` **(boolean)** — Can Comment 🔒 readonly
- `can_vote` **(boolean)** — Can Vote 🔒 readonly
- `prerequisite_user_has_completed` **(boolean)** — Has Completed Prerequisite 🔒 readonly
- `helpdesk_team_count` **(integer)** — Helpdesk Team Count 🔒 readonly
- `members_certified_count` **(integer)** — # Certified Attendees 🔒 readonly
