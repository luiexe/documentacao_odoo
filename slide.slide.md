# Slides — `slide.slide`

**Ordenação padrão:** `sequence asc, is_category asc, id asc`

---

## Campos Obrigatórios

- `name` **(char)** — Title ⚠️ obrigatório
- `channel_id` **(many2one)** — Course ⚠️ obrigatório → `slide.channel`
- `slide_category` **(selection)** — Category ⚠️ obrigatório
  > Opções: `infographic` (Image), `article` (Article), `document` (Document), `video` (Video), `quiz` (Quiz), `certification` (Certification)
- `source_type` **(selection)** — Source Type ⚠️ obrigatório
  > Opções: `local_file` (Upload from Device), `external` (Retrieve from Google Drive)

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
- `image_1920` **(binary)** — Image
- `image_1024` **(binary)** — Image 1024 🔒 readonly
- `image_512` **(binary)** — Image 512 🔒 readonly
- `image_256` **(binary)** — Image 256 🔒 readonly
- `image_128` **(binary)** — Image 128 🔒 readonly
- `active` **(boolean)** — Active
- `sequence` **(integer)** — Sequence
- `description` **(html)** — Description
- `is_preview` **(boolean)** — Allow Preview
  > The course is accessible by anyone : the users don't need to join the channel to access the content of the course.
- `completion_time` **(float)** — Duration
- `is_category` **(boolean)** — Is a category
- `quiz_first_attempt_reward` **(integer)** — Reward: first attempt
- `quiz_second_attempt_reward` **(integer)** — Reward: second attempt
- `quiz_third_attempt_reward` **(integer)** — Reward: third attempt
- `quiz_fourth_attempt_reward` **(integer)** — Reward: every attempt after the third try
- `url` **(char)** — External URL
  > URL of the Google Drive file or URL of the YouTube video
- `binary_content` **(binary)** — File
- `slide_resource_downloadable` **(boolean)** — Allow Download
  > Allow the user to download the content of the slide.
- `html_content` **(html)** — HTML Content
  > Custom HTML content for slides of category 'Article'.
- `image_binary_content` **(binary)** — Image Content
- `image_google_url` **(char)** — Image Link
  > Link of the image (we currently only support Google Drive as source)
- `slide_type` **(selection)** — Slide Type
  > Subtype of the slide category, allows more precision on the actual file type / source type.
  > Opções: `image` (Image), `article` (Article), `quiz` (Quiz), `pdf` (PDF), `sheet` (Sheet (Excel, Google Sheet, ...)), `doc` (Document (Word, Google Doc, ...)), `slides` (Slides (PowerPoint, Google Slides, ...)), `youtube_video` (YouTube Video), `google_drive_video` (Google Drive Video), `vimeo_video` (Vimeo Video), `certification` (Certification)
- `document_google_url` **(char)** — Document Link
  > Link of the document (we currently only support Google Drive as source)
- `document_binary_content` **(binary)** — PDF Content
- `video_url` **(char)** — Video Link
  > Link of the video (we support YouTube, Google Drive and Vimeo as sources)
- `date_published` **(datetime)** — Publish Date 🔒 readonly
- `likes` **(integer)** — Likes 🔒 readonly
- `dislikes` **(integer)** — Dislikes 🔒 readonly
- `slide_views` **(integer)** — # of Website Views 🔒 readonly
- `public_views` **(integer)** — # of Public Views 🔒 readonly
- `total_views` **(integer)** — # Total Views 🔒 readonly
- `nbr_document` **(integer)** — Number of Documents 🔒 readonly
- `nbr_video` **(integer)** — Number of Videos 🔒 readonly
- `nbr_infographic` **(integer)** — Number of Images 🔒 readonly
- `nbr_article` **(integer)** — Number of Articles 🔒 readonly
- `nbr_quiz` **(integer)** — Number of Quizs 🔒 readonly
- `total_slides` **(integer)** — Total Slides 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `nbr_certification` **(integer)** — Number of Certifications 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — Uploaded by → `res.users`
- `tag_ids` **(many2many)** — Tags → `slide.tag`
- `category_id` **(many2one)** — Section 🔒 readonly → `slide.slide`
- `slide_ids` **(one2many)** — Content → `slide.slide`
- `user_membership_id` **(many2one)** — Subscriber information 🔒 readonly → `slide.slide.partner`
  > Subscriber information for the current logged in user
- `question_ids` **(one2many)** — Questions → `slide.question`
- `slide_resource_ids` **(one2many)** — Additional Resource for this slide → `slide.slide.resource`
- `website_id` **(many2one)** — Website 🔒 readonly → `website`
  > Restrict to a specific website.
- `embed_ids` **(one2many)** — External Slide Embeds → `slide.embed`
- `survey_id` **(many2one)** — Certification → `survey.survey`

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
- `is_new_slide` **(boolean)** — Is New Slide 🔒 readonly
- `user_vote` **(integer)** — User vote 🔒 readonly
- `user_has_completed` **(boolean)** — Is Member 🔒 readonly
- `user_has_completed_category` **(boolean)** — Is Category Completed 🔒 readonly
- `questions_count` **(integer)** — Numbers of Questions 🔒 readonly
- `can_self_mark_completed` **(boolean)** — Can Mark Completed 🔒 readonly
  > The slide can be marked as completed even without opening it
- `can_self_mark_uncompleted` **(boolean)** — Can Mark Uncompleted 🔒 readonly
  > The slide can be marked as not completed and the progression
- `google_drive_id` **(char)** — Google Drive ID of the external URL 🔒 readonly
- `slide_icon_class` **(char)** — Slide Icon fa-class 🔒 readonly
- `video_source_type` **(selection)** — Video Source 🔒 readonly
  > Opções: `youtube` (YouTube), `google_drive` (Google Drive), `vimeo` (Vimeo)
- `youtube_id` **(char)** — Video YouTube ID 🔒 readonly
- `vimeo_id` **(char)** — Video Vimeo ID 🔒 readonly
- `embed_code` **(html)** — Embed Code 🔒 readonly
- `embed_code_external` **(html)** — External Embed Code 🔒 readonly
  > Same as 'Embed Code' but used to embed the content on an external website.
- `website_share_url` **(char)** — Share URL 🔒 readonly
- `embed_count` **(integer)** — # of Embeds 🔒 readonly
- `comments_count` **(integer)** — Number of comments 🔒 readonly
- `channel_type` **(selection)** — Channel type 🔒 readonly
  > Defines the course type (e.g., "Training" for interactive learning, or "Documentation" for resources and guides).
  > Opções: `training` (Training), `documentation` (Documentation)
- `channel_allow_comment` **(boolean)** — Allows comment 🔒 readonly
  > Allow Attendees to like and comment your content and to submit reviews on your course.
