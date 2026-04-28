# User — `res.users`

**Ordenação padrão:** `name, login`

---

## Campos Obrigatórios

- `partner_id` **(many2one)** — Related Partner ⚠️ obrigatório → `res.partner`
  > Partner-related data of the user
- `login` **(char)** — Login ⚠️ obrigatório
  > Used to log into the system
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
  > The default company for this user.
- `notification_type` **(selection)** — Notification ⚠️ obrigatório
  > Policy on how to handle Chatter notifications: - By Emails: notifications are sent to your email address - In Odoo: notifications appear in your Odoo Inbox
  > Opções: `email` (By Emails), `inbox` (In Odoo)
- `outgoing_mail_server_type` **(selection)** — Outgoing Mail Server Type ⚠️ obrigatório 🔒 readonly
  > Opções: `default` (Default), `gmail` (Gmail), `outlook` (Outlook)
- `autopost_bills` **(selection)** — Auto-post bills ⚠️ obrigatório
  > Automatically post bills for this trusted partner
  > Opções: `always` (Always), `ask` (Ask after 3 validations without edits), `never` (Never)
- `group_rfq` **(selection)** — Group RFQ ⚠️ obrigatório
  > Define if RFQ should be grouped         together based on expected arrival, except for dropship operations.          On Order: Replenishment needs will be grouped together except for MTO.          Daily: Replenishment needs will be grouped if the expected arrival is the same day          Weekly: Replenishment needs will be grouped if the expected arrival is the same week or week day          Always: Replenishment needs will always be grouped.
  > Opções: `default` (On Order), `day` (Daily), `week` (Weekly), `all` (Always)
- `group_on` **(selection)** — Week Day ⚠️ obrigatório
  > Opções: `default` (Expected Date), `1` (Monday), `2` (Tuesday), `3` (Wednesday), `4` (Thursday), `5` (Friday), `6` (Saturday), `7` (Sunday)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `password` **(char)** — Password
  > Keep empty if you don't want the user to be able to connect on the system.
- `new_password` **(char)** — Set Password
  > Specify a value only when creating a user or if you're changing the user's password, otherwise leave empty. After a change of password, the user has to login again.
- `signature` **(html)** — Email Signature
- `active` **(boolean)** — Active
- `login_date` **(datetime)** — Latest Login
- `share` **(boolean)** — Share User 🔒 readonly
  > External user with limited access, created only for the purpose of sharing data.
- `name` **(char)** — Name
- `email` **(char)** — Email
- `phone` **(char)** — Phone
- `view_group_hierarchy` **(json)** — Technical field for user group setting
- `role` **(selection)** — Role
  > Opções: `group_user` (User), `group_system` (Administrator)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `tour_enabled` **(boolean)** — Onboarding
- `color_scheme` **(selection)** — Color Scheme
  > Opções: `system` (System), `light` (Light), `dark` (Dark)
- `out_of_office_from` **(datetime)** — Out Of Office From
- `out_of_office_to` **(datetime)** — Out Of Office To
- `out_of_office_message` **(html)** — Vacation Responder
- `manual_im_status` **(selection)** — IM status manually set by the user
  > Opções: `away` (Away), `busy` (Do Not Disturb), `offline` (Offline)
- `calendar_default_privacy` **(selection)** — Calendar Default Privacy
  > Opções: `public` (Public by default), `private` (Private by default), `confidential` (Internal users only)
- `karma` **(integer)** — Karma
- `odoobot_state` **(selection)** — OdooBot Status 🔒 readonly
  > Opções: `not_initialized` (Not initialized), `onboarding_emoji` (Onboarding emoji), `onboarding_attachement` (Onboarding attachment), `onboarding_command` (Onboarding command), `onboarding_ping` (Onboarding ping), `onboarding_canned` (Onboarding canned), `idle` (Idle), `disabled` (Disabled)
- `odoobot_failed` **(boolean)** — Odoobot Failed 🔒 readonly
- `oauth_uid` **(char)** — OAuth User ID
  > Oauth Provider user_id
- `odoo_com_uid` **(char)** — Odoo.com User ID
- `sign_signature` **(binary)** — Digital Signature
- `sign_initials` **(binary)** — Digital Initials
- `sign_signature_frame` **(binary)** — Digital Signature Frame
- `sign_initials_frame` **(binary)** — Digital Initials Frame
- `helpdesk_target_closed` **(integer)** — Helpdesk Target Closed
- `helpdesk_target_rating` **(float)** — Helpdesk Target Rating
- `helpdesk_target_success` **(float)** — Helpdesk Target Success
- `work_phone` **(char)** — Work Phone
- `mobile_phone` **(char)** — Work Mobile
- `work_email` **(char)** — Work Email
- `private_street` **(char)** — Private Street
- `private_street2` **(char)** — Private Street2
- `private_city` **(char)** — Private City
- `private_zip` **(char)** — Private Zip
- `private_phone` **(char)** — Private Phone
- `private_email` **(char)** — Private Email
- `km_home_work` **(integer)** — Home-Work Distance in Km
- `emergency_contact` **(char)** — Emergency Contact
- `emergency_phone` **(char)** — Emergency Phone
- `visa_expire` **(date)** — Visa Expiration Date
- `additional_note` **(text)** — Additional Note
- `barcode` **(char)** — Badge ID
  > ID used for employee identification.
- `pin` **(char)** — PIN
  > PIN used to Check In/Out in the Kiosk Mode of the Attendance application (if enabled in Configuration) and to change the cashier in the Point of Sale application.
- `create_employee` **(boolean)** — Technical field, whether to create an employee
- `website_meta_title` **(char)** — Website meta title
- `website_meta_description` **(text)** — Website meta description
- `website_meta_keywords` **(char)** — Website meta keywords
- `website_meta_og_img` **(char)** — Website opengraph image
- `seo_name` **(char)** — Seo name
- `website_published` **(boolean)** — Visible on current website
- `is_published` **(boolean)** — Is Published
- `message_bounce` **(integer)** — Bounce
  > Counter of the number of bounced emails for this contact
- `properties` **(properties)** — Properties
- `image_1920` **(binary)** — Image
- `ref` **(char)** — Reference
- `lang` **(selection)** — Language
  > All the emails and documents sent to this contact will be translated in this language.
  > Opções: `en_US` (English (US)), `pt_BR` (Portuguese (BR) / Português (BR))
- `tz` **(selection)** — Timezone
  > When printing documents and exporting/importing data, time values are computed according to this timezone. If the timezone is not set, UTC (Coordinated Universal Time) is used. Anywhere else, time values are computed according to the time offset of your web client.
  > Opções: `Africa/Abidjan` (Africa/Abidjan), `Africa/Accra` (Africa/Accra), `Africa/Addis_Ababa` (Africa/Addis_Ababa), `Africa/Algiers` (Africa/Algiers), `Africa/Asmara` (Africa/Asmara), `Africa/Asmera` (Africa/Asmera), `Africa/Bamako` (Africa/Bamako), `Africa/Bangui` (Africa/Bangui), `Africa/Banjul` (Africa/Banjul), `Africa/Bissau` (Africa/Bissau), `Africa/Blantyre` (Africa/Blantyre), `Africa/Brazzaville` (Africa/Brazzaville), `Africa/Bujumbura` (Africa/Bujumbura), `Africa/Cairo` (Africa/Cairo), `Africa/Casablanca` (Africa/Casablanca), `Africa/Ceuta` (Africa/Ceuta), `Africa/Conakry` (Africa/Conakry), `Africa/Dakar` (Africa/Dakar), `Africa/Dar_es_Salaam` (Africa/Dar_es_Salaam), `Africa/Djibouti` (Africa/Djibouti), `Africa/Douala` (Africa/Douala), `Africa/El_Aaiun` (Africa/El_Aaiun), `Africa/Freetown` (Africa/Freetown), `Africa/Gaborone` (Africa/Gaborone), `Africa/Harare` (Africa/Harare), `Africa/Johannesburg` (Africa/Johannesburg), `Africa/Juba` (Africa/Juba), `Africa/Kampala` (Africa/Kampala), `Africa/Khartoum` (Africa/Khartoum), `Africa/Kigali` (Africa/Kigali), `Africa/Kinshasa` (Africa/Kinshasa), `Africa/Lagos` (Africa/Lagos), `Africa/Libreville` (Africa/Libreville), `Africa/Lome` (Africa/Lome), `Africa/Luanda` (Africa/Luanda), `Africa/Lubumbashi` (Africa/Lubumbashi), `Africa/Lusaka` (Africa/Lusaka), `Africa/Malabo` (Africa/Malabo), `Africa/Maputo` (Africa/Maputo), `Africa/Maseru` (Africa/Maseru), `Africa/Mbabane` (Africa/Mbabane), `Africa/Mogadishu` (Africa/Mogadishu), `Africa/Monrovia` (Africa/Monrovia), `Africa/Nairobi` (Africa/Nairobi), `Africa/Ndjamena` (Africa/Ndjamena), `Africa/Niamey` (Africa/Niamey), `Africa/Nouakchott` (Africa/Nouakchott), `Africa/Ouagadougou` (Africa/Ouagadougou), `Africa/Porto-Novo` (Africa/Porto-Novo), `Africa/Sao_Tome` (Africa/Sao_Tome), `Africa/Timbuktu` (Africa/Timbuktu), `Africa/Tripoli` (Africa/Tripoli), `Africa/Tunis` (Africa/Tunis), `Africa/Windhoek` (Africa/Windhoek), `America/Adak` (America/Adak), `America/Anchorage` (America/Anchorage), `America/Anguilla` (America/Anguilla), `America/Antigua` (America/Antigua), `America/Araguaina` (America/Araguaina), `America/Argentina/Buenos_Aires` (America/Argentina/Buenos_Aires), `America/Argentina/Catamarca` (America/Argentina/Catamarca), `America/Argentina/ComodRivadavia` (America/Argentina/ComodRivadavia), `America/Argentina/Cordoba` (America/Argentina/Cordoba), `America/Argentina/Jujuy` (America/Argentina/Jujuy), `America/Argentina/La_Rioja` (America/Argentina/La_Rioja), `America/Argentina/Mendoza` (America/Argentina/Mendoza), `America/Argentina/Rio_Gallegos` (America/Argentina/Rio_Gallegos), `America/Argentina/Salta` (America/Argentina/Salta), `America/Argentina/San_Juan` (America/Argentina/San_Juan), `America/Argentina/San_Luis` (America/Argentina/San_Luis), `America/Argentina/Tucuman` (America/Argentina/Tucuman), `America/Argentina/Ushuaia` (America/Argentina/Ushuaia), `America/Aruba` (America/Aruba), `America/Asuncion` (America/Asuncion), `America/Atikokan` (America/Atikokan), `America/Atka` (America/Atka), `America/Bahia` (America/Bahia), `America/Bahia_Banderas` (America/Bahia_Banderas), `America/Barbados` (America/Barbados), `America/Belem` (America/Belem), `America/Belize` (America/Belize), `America/Blanc-Sablon` (America/Blanc-Sablon), `America/Boa_Vista` (America/Boa_Vista), `America/Bogota` (America/Bogota), `America/Boise` (America/Boise), `America/Buenos_Aires` (America/Buenos_Aires), `America/Cambridge_Bay` (America/Cambridge_Bay), `America/Campo_Grande` (America/Campo_Grande), `America/Cancun` (America/Cancun), `America/Caracas` (America/Caracas), `America/Catamarca` (America/Catamarca), `America/Cayenne` (America/Cayenne), `America/Cayman` (America/Cayman), `America/Chicago` (America/Chicago), `America/Chihuahua` (America/Chihuahua), `America/Ciudad_Juarez` (America/Ciudad_Juarez), `America/Coral_Harbour` (America/Coral_Harbour), `America/Cordoba` (America/Cordoba), `America/Costa_Rica` (America/Costa_Rica), `America/Coyhaique` (America/Coyhaique), `America/Creston` (America/Creston), `America/Cuiaba` (America/Cuiaba), `America/Curacao` (America/Curacao), `America/Danmarkshavn` (America/Danmarkshavn), `America/Dawson` (America/Dawson), `America/Dawson_Creek` (America/Dawson_Creek), `America/Denver` (America/Denver), `America/Detroit` (America/Detroit), `America/Dominica` (America/Dominica), `America/Edmonton` (America/Edmonton), `America/Eirunepe` (America/Eirunepe), `America/El_Salvador` (America/El_Salvador), `America/Ensenada` (America/Ensenada), `America/Fort_Nelson` (America/Fort_Nelson), `America/Fort_Wayne` (America/Fort_Wayne), `America/Fortaleza` (America/Fortaleza), `America/Glace_Bay` (America/Glace_Bay), `America/Godthab` (America/Godthab), `America/Goose_Bay` (America/Goose_Bay), `America/Grand_Turk` (America/Grand_Turk), `America/Grenada` (America/Grenada), `America/Guadeloupe` (America/Guadeloupe), `America/Guatemala` (America/Guatemala), `America/Guayaquil` (America/Guayaquil), `America/Guyana` (America/Guyana), `America/Halifax` (America/Halifax), `America/Havana` (America/Havana), `America/Hermosillo` (America/Hermosillo), `America/Indiana/Indianapolis` (America/Indiana/Indianapolis), `America/Indiana/Knox` (America/Indiana/Knox), `America/Indiana/Marengo` (America/Indiana/Marengo), `America/Indiana/Petersburg` (America/Indiana/Petersburg), `America/Indiana/Tell_City` (America/Indiana/Tell_City), `America/Indiana/Vevay` (America/Indiana/Vevay), `America/Indiana/Vincennes` (America/Indiana/Vincennes), `America/Indiana/Winamac` (America/Indiana/Winamac), `America/Indianapolis` (America/Indianapolis), `America/Inuvik` (America/Inuvik), `America/Iqaluit` (America/Iqaluit), `America/Jamaica` (America/Jamaica), `America/Jujuy` (America/Jujuy), `America/Juneau` (America/Juneau), `America/Kentucky/Louisville` (America/Kentucky/Louisville), `America/Kentucky/Monticello` (America/Kentucky/Monticello), `America/Knox_IN` (America/Knox_IN), `America/Kralendijk` (America/Kralendijk), `America/La_Paz` (America/La_Paz), `America/Lima` (America/Lima), `America/Los_Angeles` (America/Los_Angeles), `America/Louisville` (America/Louisville), `America/Lower_Princes` (America/Lower_Princes), `America/Maceio` (America/Maceio), `America/Managua` (America/Managua), `America/Manaus` (America/Manaus), `America/Marigot` (America/Marigot), `America/Martinique` (America/Martinique), `America/Matamoros` (America/Matamoros), `America/Mazatlan` (America/Mazatlan), `America/Mendoza` (America/Mendoza), `America/Menominee` (America/Menominee), `America/Merida` (America/Merida), `America/Metlakatla` (America/Metlakatla), `America/Mexico_City` (America/Mexico_City), `America/Miquelon` (America/Miquelon), `America/Moncton` (America/Moncton), `America/Monterrey` (America/Monterrey), `America/Montevideo` (America/Montevideo), `America/Montreal` (America/Montreal), `America/Montserrat` (America/Montserrat), `America/Nassau` (America/Nassau), `America/New_York` (America/New_York), `America/Nipigon` (America/Nipigon), `America/Nome` (America/Nome), `America/Noronha` (America/Noronha), `America/North_Dakota/Beulah` (America/North_Dakota/Beulah), `America/North_Dakota/Center` (America/North_Dakota/Center), `America/North_Dakota/New_Salem` (America/North_Dakota/New_Salem), `America/Nuuk` (America/Nuuk), `America/Ojinaga` (America/Ojinaga), `America/Panama` (America/Panama), `America/Pangnirtung` (America/Pangnirtung), `America/Paramaribo` (America/Paramaribo), `America/Phoenix` (America/Phoenix), `America/Port-au-Prince` (America/Port-au-Prince), `America/Port_of_Spain` (America/Port_of_Spain), `America/Porto_Acre` (America/Porto_Acre), `America/Porto_Velho` (America/Porto_Velho), `America/Puerto_Rico` (America/Puerto_Rico), `America/Punta_Arenas` (America/Punta_Arenas), `America/Rainy_River` (America/Rainy_River), `America/Rankin_Inlet` (America/Rankin_Inlet), `America/Recife` (America/Recife), `America/Regina` (America/Regina), `America/Resolute` (America/Resolute), `America/Rio_Branco` (America/Rio_Branco), `America/Rosario` (America/Rosario), `America/Santa_Isabel` (America/Santa_Isabel), `America/Santarem` (America/Santarem), `America/Santiago` (America/Santiago), `America/Santo_Domingo` (America/Santo_Domingo), `America/Sao_Paulo` (America/Sao_Paulo), `America/Scoresbysund` (America/Scoresbysund), `America/Shiprock` (America/Shiprock), `America/Sitka` (America/Sitka), `America/St_Barthelemy` (America/St_Barthelemy), `America/St_Johns` (America/St_Johns), `America/St_Kitts` (America/St_Kitts), `America/St_Lucia` (America/St_Lucia), `America/St_Thomas` (America/St_Thomas), `America/St_Vincent` (America/St_Vincent), `America/Swift_Current` (America/Swift_Current), `America/Tegucigalpa` (America/Tegucigalpa), `America/Thule` (America/Thule), `America/Thunder_Bay` (America/Thunder_Bay), `America/Tijuana` (America/Tijuana), `America/Toronto` (America/Toronto), `America/Tortola` (America/Tortola), `America/Vancouver` (America/Vancouver), `America/Virgin` (America/Virgin), `America/Whitehorse` (America/Whitehorse), `America/Winnipeg` (America/Winnipeg), `America/Yakutat` (America/Yakutat), `America/Yellowknife` (America/Yellowknife), `Antarctica/Casey` (Antarctica/Casey), `Antarctica/Davis` (Antarctica/Davis), `Antarctica/DumontDUrville` (Antarctica/DumontDUrville), `Antarctica/Macquarie` (Antarctica/Macquarie), `Antarctica/Mawson` (Antarctica/Mawson), `Antarctica/McMurdo` (Antarctica/McMurdo), `Antarctica/Palmer` (Antarctica/Palmer), `Antarctica/Rothera` (Antarctica/Rothera), `Antarctica/South_Pole` (Antarctica/South_Pole), `Antarctica/Syowa` (Antarctica/Syowa), `Antarctica/Troll` (Antarctica/Troll), `Antarctica/Vostok` (Antarctica/Vostok), `Arctic/Longyearbyen` (Arctic/Longyearbyen), `Asia/Aden` (Asia/Aden), `Asia/Almaty` (Asia/Almaty), `Asia/Amman` (Asia/Amman), `Asia/Anadyr` (Asia/Anadyr), `Asia/Aqtau` (Asia/Aqtau), `Asia/Aqtobe` (Asia/Aqtobe), `Asia/Ashgabat` (Asia/Ashgabat), `Asia/Ashkhabad` (Asia/Ashkhabad), `Asia/Atyrau` (Asia/Atyrau), `Asia/Baghdad` (Asia/Baghdad), `Asia/Bahrain` (Asia/Bahrain), `Asia/Baku` (Asia/Baku), `Asia/Bangkok` (Asia/Bangkok), `Asia/Barnaul` (Asia/Barnaul), `Asia/Beirut` (Asia/Beirut), `Asia/Bishkek` (Asia/Bishkek), `Asia/Brunei` (Asia/Brunei), `Asia/Calcutta` (Asia/Calcutta), `Asia/Chita` (Asia/Chita), `Asia/Choibalsan` (Asia/Choibalsan), `Asia/Chongqing` (Asia/Chongqing), `Asia/Chungking` (Asia/Chungking), `Asia/Colombo` (Asia/Colombo), `Asia/Dacca` (Asia/Dacca), `Asia/Damascus` (Asia/Damascus), `Asia/Dhaka` (Asia/Dhaka), `Asia/Dili` (Asia/Dili), `Asia/Dubai` (Asia/Dubai), `Asia/Dushanbe` (Asia/Dushanbe), `Asia/Famagusta` (Asia/Famagusta), `Asia/Gaza` (Asia/Gaza), `Asia/Harbin` (Asia/Harbin), `Asia/Hebron` (Asia/Hebron), `Asia/Ho_Chi_Minh` (Asia/Ho_Chi_Minh), `Asia/Hong_Kong` (Asia/Hong_Kong), `Asia/Hovd` (Asia/Hovd), `Asia/Irkutsk` (Asia/Irkutsk), `Asia/Istanbul` (Asia/Istanbul), `Asia/Jakarta` (Asia/Jakarta), `Asia/Jayapura` (Asia/Jayapura), `Asia/Jerusalem` (Asia/Jerusalem), `Asia/Kabul` (Asia/Kabul), `Asia/Kamchatka` (Asia/Kamchatka), `Asia/Karachi` (Asia/Karachi), `Asia/Kashgar` (Asia/Kashgar), `Asia/Kathmandu` (Asia/Kathmandu), `Asia/Katmandu` (Asia/Katmandu), `Asia/Khandyga` (Asia/Khandyga), `Asia/Kolkata` (Asia/Kolkata), `Asia/Krasnoyarsk` (Asia/Krasnoyarsk), `Asia/Kuala_Lumpur` (Asia/Kuala_Lumpur), `Asia/Kuching` (Asia/Kuching), `Asia/Kuwait` (Asia/Kuwait), `Asia/Macao` (Asia/Macao), `Asia/Macau` (Asia/Macau), `Asia/Magadan` (Asia/Magadan), `Asia/Makassar` (Asia/Makassar), `Asia/Manila` (Asia/Manila), `Asia/Muscat` (Asia/Muscat), `Asia/Nicosia` (Asia/Nicosia), `Asia/Novokuznetsk` (Asia/Novokuznetsk), `Asia/Novosibirsk` (Asia/Novosibirsk), `Asia/Omsk` (Asia/Omsk), `Asia/Oral` (Asia/Oral), `Asia/Phnom_Penh` (Asia/Phnom_Penh), `Asia/Pontianak` (Asia/Pontianak), `Asia/Pyongyang` (Asia/Pyongyang), `Asia/Qatar` (Asia/Qatar), `Asia/Qostanay` (Asia/Qostanay), `Asia/Qyzylorda` (Asia/Qyzylorda), `Asia/Rangoon` (Asia/Rangoon), `Asia/Riyadh` (Asia/Riyadh), `Asia/Saigon` (Asia/Saigon), `Asia/Sakhalin` (Asia/Sakhalin), `Asia/Samarkand` (Asia/Samarkand), `Asia/Seoul` (Asia/Seoul), `Asia/Shanghai` (Asia/Shanghai), `Asia/Singapore` (Asia/Singapore), `Asia/Srednekolymsk` (Asia/Srednekolymsk), `Asia/Taipei` (Asia/Taipei), `Asia/Tashkent` (Asia/Tashkent), `Asia/Tbilisi` (Asia/Tbilisi), `Asia/Tehran` (Asia/Tehran), `Asia/Tel_Aviv` (Asia/Tel_Aviv), `Asia/Thimbu` (Asia/Thimbu), `Asia/Thimphu` (Asia/Thimphu), `Asia/Tokyo` (Asia/Tokyo), `Asia/Tomsk` (Asia/Tomsk), `Asia/Ujung_Pandang` (Asia/Ujung_Pandang), `Asia/Ulaanbaatar` (Asia/Ulaanbaatar), `Asia/Ulan_Bator` (Asia/Ulan_Bator), `Asia/Urumqi` (Asia/Urumqi), `Asia/Ust-Nera` (Asia/Ust-Nera), `Asia/Vientiane` (Asia/Vientiane), `Asia/Vladivostok` (Asia/Vladivostok), `Asia/Yakutsk` (Asia/Yakutsk), `Asia/Yangon` (Asia/Yangon), `Asia/Yekaterinburg` (Asia/Yekaterinburg), `Asia/Yerevan` (Asia/Yerevan), `Atlantic/Azores` (Atlantic/Azores), `Atlantic/Bermuda` (Atlantic/Bermuda), `Atlantic/Canary` (Atlantic/Canary), `Atlantic/Cape_Verde` (Atlantic/Cape_Verde), `Atlantic/Faeroe` (Atlantic/Faeroe), `Atlantic/Faroe` (Atlantic/Faroe), `Atlantic/Jan_Mayen` (Atlantic/Jan_Mayen), `Atlantic/Madeira` (Atlantic/Madeira), `Atlantic/Reykjavik` (Atlantic/Reykjavik), `Atlantic/South_Georgia` (Atlantic/South_Georgia), `Atlantic/St_Helena` (Atlantic/St_Helena), `Atlantic/Stanley` (Atlantic/Stanley), `Australia/ACT` (Australia/ACT), `Australia/Adelaide` (Australia/Adelaide), `Australia/Brisbane` (Australia/Brisbane), `Australia/Broken_Hill` (Australia/Broken_Hill), `Australia/Canberra` (Australia/Canberra), `Australia/Currie` (Australia/Currie), `Australia/Darwin` (Australia/Darwin), `Australia/Eucla` (Australia/Eucla), `Australia/Hobart` (Australia/Hobart), `Australia/LHI` (Australia/LHI), `Australia/Lindeman` (Australia/Lindeman), `Australia/Lord_Howe` (Australia/Lord_Howe), `Australia/Melbourne` (Australia/Melbourne), `Australia/NSW` (Australia/NSW), `Australia/North` (Australia/North), `Australia/Perth` (Australia/Perth), `Australia/Queensland` (Australia/Queensland), `Australia/South` (Australia/South), `Australia/Sydney` (Australia/Sydney), `Australia/Tasmania` (Australia/Tasmania), `Australia/Victoria` (Australia/Victoria), `Australia/West` (Australia/West), `Australia/Yancowinna` (Australia/Yancowinna), `Brazil/Acre` (Brazil/Acre), `Brazil/DeNoronha` (Brazil/DeNoronha), `Brazil/East` (Brazil/East), `Brazil/West` (Brazil/West), `CET` (CET), `CST6CDT` (CST6CDT), `Canada/Atlantic` (Canada/Atlantic), `Canada/Central` (Canada/Central), `Canada/Eastern` (Canada/Eastern), `Canada/Mountain` (Canada/Mountain), `Canada/Newfoundland` (Canada/Newfoundland), `Canada/Pacific` (Canada/Pacific), `Canada/Saskatchewan` (Canada/Saskatchewan), `Canada/Yukon` (Canada/Yukon), `Chile/Continental` (Chile/Continental), `Chile/EasterIsland` (Chile/EasterIsland), `Cuba` (Cuba), `EET` (EET), `EST` (EST), `EST5EDT` (EST5EDT), `Egypt` (Egypt), `Eire` (Eire), `Europe/Amsterdam` (Europe/Amsterdam), `Europe/Andorra` (Europe/Andorra), `Europe/Astrakhan` (Europe/Astrakhan), `Europe/Athens` (Europe/Athens), `Europe/Belfast` (Europe/Belfast), `Europe/Belgrade` (Europe/Belgrade), `Europe/Berlin` (Europe/Berlin), `Europe/Bratislava` (Europe/Bratislava), `Europe/Brussels` (Europe/Brussels), `Europe/Bucharest` (Europe/Bucharest), `Europe/Budapest` (Europe/Budapest), `Europe/Busingen` (Europe/Busingen), `Europe/Chisinau` (Europe/Chisinau), `Europe/Copenhagen` (Europe/Copenhagen), `Europe/Dublin` (Europe/Dublin), `Europe/Gibraltar` (Europe/Gibraltar), `Europe/Guernsey` (Europe/Guernsey), `Europe/Helsinki` (Europe/Helsinki), `Europe/Isle_of_Man` (Europe/Isle_of_Man), `Europe/Istanbul` (Europe/Istanbul), `Europe/Jersey` (Europe/Jersey), `Europe/Kaliningrad` (Europe/Kaliningrad), `Europe/Kiev` (Europe/Kiev), `Europe/Kirov` (Europe/Kirov), `Europe/Kyiv` (Europe/Kyiv), `Europe/Lisbon` (Europe/Lisbon), `Europe/Ljubljana` (Europe/Ljubljana), `Europe/London` (Europe/London), `Europe/Luxembourg` (Europe/Luxembourg), `Europe/Madrid` (Europe/Madrid), `Europe/Malta` (Europe/Malta), `Europe/Mariehamn` (Europe/Mariehamn), `Europe/Minsk` (Europe/Minsk), `Europe/Monaco` (Europe/Monaco), `Europe/Moscow` (Europe/Moscow), `Europe/Nicosia` (Europe/Nicosia), `Europe/Oslo` (Europe/Oslo), `Europe/Paris` (Europe/Paris), `Europe/Podgorica` (Europe/Podgorica), `Europe/Prague` (Europe/Prague), `Europe/Riga` (Europe/Riga), `Europe/Rome` (Europe/Rome), `Europe/Samara` (Europe/Samara), `Europe/San_Marino` (Europe/San_Marino), `Europe/Sarajevo` (Europe/Sarajevo), `Europe/Saratov` (Europe/Saratov), `Europe/Simferopol` (Europe/Simferopol), `Europe/Skopje` (Europe/Skopje), `Europe/Sofia` (Europe/Sofia), `Europe/Stockholm` (Europe/Stockholm), `Europe/Tallinn` (Europe/Tallinn), `Europe/Tirane` (Europe/Tirane), `Europe/Tiraspol` (Europe/Tiraspol), `Europe/Ulyanovsk` (Europe/Ulyanovsk), `Europe/Uzhgorod` (Europe/Uzhgorod), `Europe/Vaduz` (Europe/Vaduz), `Europe/Vatican` (Europe/Vatican), `Europe/Vienna` (Europe/Vienna), `Europe/Vilnius` (Europe/Vilnius), `Europe/Volgograd` (Europe/Volgograd), `Europe/Warsaw` (Europe/Warsaw), `Europe/Zagreb` (Europe/Zagreb), `Europe/Zaporozhye` (Europe/Zaporozhye), `Europe/Zurich` (Europe/Zurich), `GB` (GB), `GB-Eire` (GB-Eire), `GMT` (GMT), `GMT+0` (GMT+0), `GMT-0` (GMT-0), `GMT0` (GMT0), `Greenwich` (Greenwich), `HST` (HST), `Hongkong` (Hongkong), `Iceland` (Iceland), `Indian/Antananarivo` (Indian/Antananarivo), `Indian/Chagos` (Indian/Chagos), `Indian/Christmas` (Indian/Christmas), `Indian/Cocos` (Indian/Cocos), `Indian/Comoro` (Indian/Comoro), `Indian/Kerguelen` (Indian/Kerguelen), `Indian/Mahe` (Indian/Mahe), `Indian/Maldives` (Indian/Maldives), `Indian/Mauritius` (Indian/Mauritius), `Indian/Mayotte` (Indian/Mayotte), `Indian/Reunion` (Indian/Reunion), `Iran` (Iran), `Israel` (Israel), `Jamaica` (Jamaica), `Japan` (Japan), `Kwajalein` (Kwajalein), `Libya` (Libya), `MET` (MET), `MST` (MST), `MST7MDT` (MST7MDT), `Mexico/BajaNorte` (Mexico/BajaNorte), `Mexico/BajaSur` (Mexico/BajaSur), `Mexico/General` (Mexico/General), `NZ` (NZ), `NZ-CHAT` (NZ-CHAT), `Navajo` (Navajo), `PRC` (PRC), `PST8PDT` (PST8PDT), `Pacific/Apia` (Pacific/Apia), `Pacific/Auckland` (Pacific/Auckland), `Pacific/Bougainville` (Pacific/Bougainville), `Pacific/Chatham` (Pacific/Chatham), `Pacific/Chuuk` (Pacific/Chuuk), `Pacific/Easter` (Pacific/Easter), `Pacific/Efate` (Pacific/Efate), `Pacific/Enderbury` (Pacific/Enderbury), `Pacific/Fakaofo` (Pacific/Fakaofo), `Pacific/Fiji` (Pacific/Fiji), `Pacific/Funafuti` (Pacific/Funafuti), `Pacific/Galapagos` (Pacific/Galapagos), `Pacific/Gambier` (Pacific/Gambier), `Pacific/Guadalcanal` (Pacific/Guadalcanal), `Pacific/Guam` (Pacific/Guam), `Pacific/Honolulu` (Pacific/Honolulu), `Pacific/Johnston` (Pacific/Johnston), `Pacific/Kanton` (Pacific/Kanton), `Pacific/Kiritimati` (Pacific/Kiritimati), `Pacific/Kosrae` (Pacific/Kosrae), `Pacific/Kwajalein` (Pacific/Kwajalein), `Pacific/Majuro` (Pacific/Majuro), `Pacific/Marquesas` (Pacific/Marquesas), `Pacific/Midway` (Pacific/Midway), `Pacific/Nauru` (Pacific/Nauru), `Pacific/Niue` (Pacific/Niue), `Pacific/Norfolk` (Pacific/Norfolk), `Pacific/Noumea` (Pacific/Noumea), `Pacific/Pago_Pago` (Pacific/Pago_Pago), `Pacific/Palau` (Pacific/Palau), `Pacific/Pitcairn` (Pacific/Pitcairn), `Pacific/Pohnpei` (Pacific/Pohnpei), `Pacific/Ponape` (Pacific/Ponape), `Pacific/Port_Moresby` (Pacific/Port_Moresby), `Pacific/Rarotonga` (Pacific/Rarotonga), `Pacific/Saipan` (Pacific/Saipan), `Pacific/Samoa` (Pacific/Samoa), `Pacific/Tahiti` (Pacific/Tahiti), `Pacific/Tarawa` (Pacific/Tarawa), `Pacific/Tongatapu` (Pacific/Tongatapu), `Pacific/Truk` (Pacific/Truk), `Pacific/Wake` (Pacific/Wake), `Pacific/Wallis` (Pacific/Wallis), `Pacific/Yap` (Pacific/Yap), `Poland` (Poland), `Portugal` (Portugal), `ROC` (ROC), `ROK` (ROK), `Singapore` (Singapore), `Turkey` (Turkey), `UCT` (UCT), `US/Alaska` (US/Alaska), `US/Aleutian` (US/Aleutian), `US/Arizona` (US/Arizona), `US/Central` (US/Central), `US/East-Indiana` (US/East-Indiana), `US/Eastern` (US/Eastern), `US/Hawaii` (US/Hawaii), `US/Indiana-Starke` (US/Indiana-Starke), `US/Michigan` (US/Michigan), `US/Mountain` (US/Mountain), `US/Pacific` (US/Pacific), `US/Samoa` (US/Samoa), `UTC` (UTC), `Universal` (Universal), `W-SU` (W-SU), `WET` (WET), `Zulu` (Zulu), `Etc/GMT` (Etc/GMT), `Etc/GMT+0` (Etc/GMT+0), `Etc/GMT+1` (Etc/GMT+1), `Etc/GMT+10` (Etc/GMT+10), `Etc/GMT+11` (Etc/GMT+11), `Etc/GMT+12` (Etc/GMT+12), `Etc/GMT+2` (Etc/GMT+2), `Etc/GMT+3` (Etc/GMT+3), `Etc/GMT+4` (Etc/GMT+4), `Etc/GMT+5` (Etc/GMT+5), `Etc/GMT+6` (Etc/GMT+6), `Etc/GMT+7` (Etc/GMT+7), `Etc/GMT+8` (Etc/GMT+8), `Etc/GMT+9` (Etc/GMT+9), `Etc/GMT-0` (Etc/GMT-0), `Etc/GMT-1` (Etc/GMT-1), `Etc/GMT-10` (Etc/GMT-10), `Etc/GMT-11` (Etc/GMT-11), `Etc/GMT-12` (Etc/GMT-12), `Etc/GMT-13` (Etc/GMT-13), `Etc/GMT-14` (Etc/GMT-14), `Etc/GMT-2` (Etc/GMT-2), `Etc/GMT-3` (Etc/GMT-3), `Etc/GMT-4` (Etc/GMT-4), `Etc/GMT-5` (Etc/GMT-5), `Etc/GMT-6` (Etc/GMT-6), `Etc/GMT-7` (Etc/GMT-7), `Etc/GMT-8` (Etc/GMT-8), `Etc/GMT-9` (Etc/GMT-9), `Etc/GMT0` (Etc/GMT0), `Etc/Greenwich` (Etc/Greenwich), `Etc/UCT` (Etc/UCT), `Etc/UTC` (Etc/UTC), `Etc/Universal` (Etc/Universal), `Etc/Zulu` (Etc/Zulu)
- `vat` **(char)** — Identification Number
  > Identification Number for selected type
- `company_registry` **(char)** — Company ID
  > The registry number of the company. Use it if it is different from the Tax ID. It must be unique across all partners of a same country
- `website` **(char)** — Website Link
- `comment` **(html)** — Notes
- `employee` **(boolean)** — Employee
  > Whether this contact is an Employee.
- `function` **(char)** — Job Position
- `type` **(selection)** — Address Type
  > Opções: `contact` (Contact), `invoice` (Invoice), `delivery` (Delivery), `other` (Other)
- `street` **(char)** — Street
- `street2` **(char)** — Street2
- `zip` **(char)** — Zip
- `city` **(char)** — City
- `partner_latitude` **(float)** — Geo Latitude
- `partner_longitude` **(float)** — Geo Longitude
- `is_company` **(boolean)** — Is a Company
  > Check if the contact is a company, otherwise it is a person
- `company_type` **(selection)** — Company Type
  > Opções: `person` (Person), `company` (Company)
- `color` **(integer)** — Color Index
- `company_name` **(char)** — Company Name
- `date_localization` **(date)** — Geolocation Date
- `signup_type` **(char)** — Signup Token Type
- `calendar_last_notif_ack` **(datetime)** — Last notification marked as read from base Calendar
- `phone_mobile_search` **(char)** — Phone Number
- `street_name` **(char)** — Street Name
- `street_number` **(char)** — House
- `street_number2` **(char)** — Door
- `trust` **(selection)** — Degree of trust you have in this debtor
  > Opções: `good` (Good Debtor), `normal` (Normal Debtor), `bad` (Bad Debtor)
- `ignore_abnormal_invoice_date` **(boolean)** — Ignore Abnormal Invoice Date
- `ignore_abnormal_invoice_amount` **(boolean)** — Ignore Abnormal Invoice Amount
- `invoice_sending_method` **(selection)** — Invoice sending
  > Opções: `manual` (Manual), `email` (by Email), `snailmail` (by Post)
- `invoice_edi_format` **(selection)** — eInvoice format
  > Opções: `facturx` (France (FacturX)), `ubl_bis3` (EU Standard (Peppol Bis 3.0)), `zugferd` (Germany (ZUGFeRD)), `xrechnung` (Germany (XRechnung)), `nlcius` (Netherlands (NLCIUS)), `ubl_a_nz` (Australia (BIS Billing 3.0 A-NZ)), `ubl_sg` (Singapore (BIS Billing 3.0 SG))
- `invoice_edi_format_store` **(char)** — Invoice Edi Format Store
- `display_invoice_edi_format` **(boolean)** — Display Invoice Edi Format
- `display_invoice_template_pdf_report_id` **(boolean)** — Display Invoice Template Pdf Report
- `supplier_rank` **(integer)** — Supplier Rank
- `customer_rank` **(integer)** — Customer Rank
- `picking_warn_msg` **(text)** — Message for Stock Picking
- `peppol_endpoint` **(char)** — Peppol Endpoint
  > Unique identifier used by the BIS Billing 3.0 and its derivatives, also known as 'Endpoint ID'.
- `peppol_eas` **(selection)** — Peppol e-address (EAS)
  > Code used to identify the Endpoint for BIS Billing 3.0 and its derivatives.              List available at https://docs.peppol.eu/poacc/billing/3.0/codelist/eas/
  > Opções: `9923` (Albania VAT), `9922` (Andorra VAT), `0151` (Australia ABN), `9914` (Austria UID), `9915` (Austria VOKZ), `0208` (Belgian Company Registry), `9925` (Belgian VAT), `9924` (Bosnia and Herzegovina VAT), `9926` (Bulgaria VAT), `9934` (Croatia VAT), `9928` (Cyprus VAT), `9929` (Czech Republic VAT), `0096` (Denmark P), `0184` (Denmark CVR), `0198` (Denmark SE), `0191` (Estonia Company code), `9931` (Estonia VAT), `0037` (Finland LY-tunnus), `0216` (Finland OVT code), `0213` (Finland VAT), `0002` (France SIRENE), `0009` (France SIRET), `9957` (France VAT), `0225` (France FRCTC Electronic Address), `0240` (France Register of legal persons), `0246` (German Electronic Business Address), `0204` (Germany Leitweg-ID), `9930` (Germany VAT), `9933` (Greece VAT), `9910` (Hungary VAT), `0196` (Iceland Kennitala), `9935` (Ireland VAT), `0211` (Italia Partita IVA), `0097` (Italia FTI), `0188` (Japan SST), `0221` (Japan IIN), `0218` (Latvia Unified registration number), `9939` (Latvia VAT), `9936` (Liechtenstein VAT), `0200` (Lithuania JAK), `9937` (Lithuania VAT), `9938` (Luxembourg VAT), `9942` (Macedonia VAT), `0230` (Malaysia), `9943` (Malta VAT), `9940` (Monaco VAT), `9941` (Montenegro VAT), `0106` (Netherlands KvK), `0190` (Netherlands OIN), `9944` (Netherlands VAT), `0244` (Nigeria Tax Identification), `0192` (Norway Org.nr.), `9945` (Poland VAT), `9946` (Portugal VAT), `9947` (Romania VAT), `9948` (Serbia VAT), `0195` (Singapore UEN), `0245` (SK Tax identification number (DIČ)), `9949` (Slovenia VAT), `9950` (Slovakia VAT), `9920` (Spain VAT), `0007` (Sweden Org.nr.), `9955` (Sweden VAT), `9927` (Swiss VAT), `0183` (Swiss UIDB), `9952` (Turkey VAT), `0235` (UAE Tax Identification Number (TIN)), `9932` (United Kingdom VAT), `9959` (USA EIN), `0060` (DUNS Number), `0088` (EAN Location Code), `0130` (Directorates of the European Commission), `0135` (SIA Object Identifiers), `0142` (SECETI Object Identifiers), `0193` (UBL.BE party identifier), `0199` (Legal Entity Identifier (LEI)), `0201` (Codice Univoco Unità Organizzativa iPA), `0202` (Indirizzo di Posta Elettronica Certificata), `0209` (GS1 identification keys), `0210` (Codice Fiscale), `9913` (Business Registers Network), `9918` (S.W.I.F.T), `9919` (Kennziffer des Unternehmensregisters), `9951` (San Marino VAT), `9953` (Vatican VAT), `AN` (O.F.T.P. (ODETTE File Transfer Protocol)), `AQ` (X.400 address for mail text), `AS` (AS2 exchange), `AU` (File Transfer Protocol), `EM` (Electronic mail)
- `vies_valid` **(boolean)** — Intra-Community Valid
  > European VAT numbers are automatically checked on the VIES database.
- `purchase_warn_msg` **(text)** — Message for Purchase Order
- `receipt_reminder_email` **(boolean)** — Receipt Reminder
  > Automatically send a confirmation email to the vendor X days before the expected receipt date, asking him to confirm the exact date.
- `reminder_date_before_receipt` **(integer)** — Days Before Receipt
  > Number of days to send reminder email before the promised receipt date
- `website_description` **(html)** — Website Partner Full Description
- `website_short_description` **(text)** — Website Partner Short Description
- `suggest_based_on` **(char)** — Suggest Based On
- `suggest_days` **(integer)** — Suggest Days
- `suggest_percent` **(integer)** — Suggest Percent
- `sale_warn_msg` **(text)** — Message for Sales Order
- `followup_next_action_date` **(date)** — Next reminder
  > No follow-up action will be taken before this date.                 Sending a reminder will set this date depending on the levels configuration, and you can change it manually.
- `followup_reminder_type` **(selection)** — Reminders
  > Opções: `automatic` (Automatic), `manual` (Manual)
- `is_pickup_location` **(boolean)** — Is Pickup Location
- `l10n_br_ie_code` **(char)** — IE
  > State Tax Identification Number. Should contain 9-14 digits.
- `l10n_br_im_code` **(char)** — IM
  > Municipal Tax Identification Number
- `l10n_br_isuf_code` **(char)** — SUFRAMA code
  > SUFRAMA registration number.
- `is_created_by_ocr` **(boolean)** — Is Created By Ocr
- `l10n_br_activity_sector` **(selection)** — Main Activity Sector
  > Brazil: List of main Activity Sectors of the contact
  > Opções: `armedForces` (armedForces), `auctioneer` (auctioneer), `audiovisualIndustry` (audiovisualIndustry), `bondedWarehouse` (bondedWarehouse), `broadcastingIndustry` (broadcastingIndustry), `construction` (construction), `coops` (coops), `distributor` (distributor), `distributionCenter` (distributionCenter), `electricityDistributor` (electricityDistributor), `energyGeneration` (energyGeneration), `extractor` (extractor), `farmCoop` (farmCoop), `filmIndustry` (filmIndustry), `finalConsumer` (finalConsumer), `fuelDistributor` (fuelDistributor), `generalWarehouse` (generalWarehouse), `importer` (importer), `industry` (industry), `itaipubiNacional` (itaipubiNacional), `maritimeService` (maritimeService), `mealSupplier` (mealSupplier), `nonProfitEntity` (nonProfitEntity), `pharmaDistributor` (pharmaDistributor), `publicAgency` (publicAgency), `religiousEstablishment` (religiousEstablishment), `retail` (retail), `ruralProducer` (ruralProducer), `securityPublicAgency` (securityPublicAgency), `service` (service), `stockWarehouse` (stockWarehouse), `telco` (telco), `transporter` (transporter), `waterDistributor` (waterDistributor), `wholesale` (wholesale), `commerce` (commerce)
- `l10n_br_taxpayer` **(selection)** — ICMS Taxpayer Type
  > Brazil: Taxpayer Type informs whether the contact is within the ICMS regime, if it is Exempt, or if it is a Non-Taxpayer
  > Opções: `icms` (ICMS Taxpayer), `exempt` (Taxpayer Exempt), `non` (Non-Taxpayer)
- `l10n_br_tax_regime` **(selection)** — Tax Regime
  > Brazil: Contact FederalTax Regime
  > Opções: `realProfit` (realProfit), `estimatedProfit` (estimatedProfit), `simplified` (simplified), `simplifiedHybrid` (simplifiedHybrid), `simplifiedOverGrossthreshold` (simplifiedOverGrossthreshold), `simplifiedEntrepreneur` (simplifiedEntrepreneur), `notApplicable` (notApplicable), `individual` (individual), `variable` (variable)
- `l10n_br_subject_cofins` **(selection)** — COFINS Details
  > Brazil: There are cases where both seller, buyer, and items are taxable but a special situation forces the transaction to be exempt especially for PIS and COFINS. This attribute allows users to identify such scenarios and trigger the exemption despite all other settings.
  > Opções: `T` (Taxable), `N` (Not Taxable), `Z` (Taxable With Rate=0.00), `E` (Exempt), `H` (Suspended)
- `l10n_br_subject_pis` **(selection)** — PIS Details
  > Brazil: There are cases where both seller, buyer, and items are taxable but a special situation forces the transaction to be exempt especially for PIS and COFINS. This attribute allows users to identify such scenarios and trigger the exemption despite all other settings.
  > Opções: `T` (Taxable), `N` (Not Taxable), `Z` (Taxable With Rate=0.00), `E` (Exempt), `H` (Suspended)
- `l10n_br_is_subject_csll` **(boolean)** — CSLL Taxable
  > Brazil: If not checked, then it will be treated as Exempt. There are cases where both seller, buyer, and items are taxable but a special situation forces the transaction to be CSLL exempt. This attribute allows users to identify such scenarios and trigger the exemption despite all other settings.
- `l10n_br_iss_simples_rate` **(float)** — ISS Simplified Rate
  > Brazil: In case the customer or the seller - company - is in the Simplified Regime, the seller - company - needs to inform the ISS rate.
- `l10n_br_is_cbs_ibs_taxpayer` **(boolean)** — CBS/IBS Taxpayer
  > Brazil: Indicates that this entity is subject to CBS/IBS taxation. Used for exempt operations or special regimes.
- `l10n_br_is_cbs_ibs_normal` **(boolean)** — CBS/IBS Normal
  > Brazil: Indicates whether the contact or company under the simplified regime is classified as Normal or Mixed taxation. When enabled, it means the entity follows the Normal regime; when disabled, it indicates the Mixed regime.
- `l10n_br_cbs_credit` **(float)** — CBS Presumed Credit (%)
  > Brazil: Percentage of presumed CBS credit for entities under Simples Nacional "misto" regime.
- `l10n_br_ibs_credit` **(float)** — IBS Presumed Credit (%)
  > Brazil: Percentage of presumed IBS credit for entities under Simples Nacional "misto" regime.
- `l10n_br_is_cashback_applied` **(boolean)** — Apply Cashback
  > Brazil: Enables CBS/IBS cashback calculation for eligible consumers in outbound operations.
- `l10n_br_entity_type` **(selection)** — Entity Type
  > Brazil: Defines the type of entity.
  > Opções: `individual` (Individual), `business` (Business), `foreign` (Foreign), `federalGovernment` (Federal Government), `stateGovernment` (State Government), `cityGovernment` (City Government), `mixedCapital` (Mixed Capital), `coops` (Coops)
- `x_enviado_webhook` **(boolean)** — false

## Relacionamentos

- `api_key_ids` **(one2many)** — API Keys → `res.users.apikeys`
- `action_id` **(many2one)** — Home Action → `ir.actions.actions`
  > If specified, this action will be opened at log on for this user, in addition to the standard menu.
- `log_ids` **(one2many)** — User log entries → `res.users.log`
- `device_ids` **(one2many)** — User devices → `res.device`
- `res_users_settings_ids` **(one2many)** — Res Users Settings → `res.users.settings`
- `res_users_settings_id` **(many2one)** — Settings 🔒 readonly → `res.users.settings`
- `company_ids` **(many2many)** — Companies → `res.company`
- `group_ids` **(many2many)** — Groups → `res.groups`
  > Groups explicitly assigned to the user
- `all_group_ids` **(many2many)** — Groups and implied groups 🔒 readonly → `res.groups`
- `totp_trusted_device_ids` **(one2many)** — Trusted Devices → `auth_totp.device`
- `resource_ids` **(one2many)** — Resources → `resource.resource`
- `resource_calendar_id` **(many2one)** — Default Working Hours → `resource.calendar`
  > Define the working schedule of the resource. If not set, the resource will have fully flexible working hours.
- `auth_passkey_key_ids` **(one2many)** — Auth Passkey Key → `auth.passkey.key`
- `role_ids` **(many2many)** — User Roles → `res.role`
  > Users are notified whenever one of their roles is @-mentioned in a conversation.
- `presence_ids` **(one2many)** — Presence → `mail.presence`
- `outgoing_mail_server_id` **(many2one)** — Outgoing Mail Server 🔒 readonly → `ir.mail_server`
- `karma_tracking_ids` **(one2many)** — Karma Changes → `gamification.karma.tracking`
- `badge_ids` **(one2many)** — Badges → `gamification.badge.user`
- `rank_id` **(many2one)** — Rank → `gamification.karma.rank`
- `next_rank_id` **(many2one)** — Next Rank → `gamification.karma.rank`
- `crm_team_ids` **(many2many)** — Sales Teams 🔒 readonly → `crm.team`
- `crm_team_member_ids` **(one2many)** — Sales Team Members → `crm.team.member`
- `sale_team_id` **(many2one)** — User Sales Team 🔒 readonly → `crm.team`
  > Main user sales team. Used notably for pipeline, or to set sales team in invoicing or subscription.
- `employee_ids` **(one2many)** — Related employee → `hr.employee`
- `employee_id` **(many2one)** — Company employee 🔒 readonly → `hr.employee`
- `category_ids` **(many2many)** — Employee Tags → `hr.employee.category`
- `work_contact_id` **(many2one)** — Work Contact → `res.partner`
- `work_location_id` **(many2one)** — Work Location → `hr.work.location`
- `private_state_id` **(many2one)** — Private State → `res.country.state`
- `private_country_id` **(many2one)** — Private Country → `res.country`
- `employee_bank_account_ids` **(many2many)** — Employee's Bank Accounts → `res.partner.bank`
  > Employee bank accounts to pay salaries
- `employee_resource_calendar_id` **(many2one)** — Employee's Working Hours 🔒 readonly → `resource.calendar`
- `bank_account_ids` **(many2many)** — Bank Accounts 🔒 readonly → `res.partner.bank`
  > Employee bank accounts to pay salaries
- `create_employee_id` **(many2one)** — Technical field, bind user to this employee on create → `hr.employee`
- `favorite_project_ids` **(many2many)** — Favorite Projects → `project.project`
- `website_id` **(many2one)** — Website → `website`
  > Restrict to a specific website.
- `goal_ids` **(one2many)** — Goal → `gamification.goal`
- `monday_location_id` **(many2one)** — Mondays → `hr.work.location`
- `tuesday_location_id` **(many2one)** — Tuesdays → `hr.work.location`
- `wednesday_location_id` **(many2one)** — Wednesdays → `hr.work.location`
- `thursday_location_id` **(many2one)** — Thursdays → `hr.work.location`
- `friday_location_id` **(many2one)** — Fridays → `hr.work.location`
- `saturday_location_id` **(many2one)** — Saturdays → `hr.work.location`
- `sunday_location_id` **(many2one)** — Sundays → `hr.work.location`
- `task_ids` **(many2many)** — Assigned Tasks → `project.task`
- `employee_skill_ids` **(one2many)** — Skills 🔒 readonly → `hr.employee.skill`
- `property_warehouse_id` **(many2one)** — Default Warehouse → `stock.warehouse`
- `commission_plan_users_ids` **(one2many)** — Commission plans → `sale.commission.plan.user`
- `filtered_commission_plan_users_ids` **(one2many)** — Filtered Commission Plan Users 🔒 readonly → `sale.commission.plan.user`
- `properties_base_definition_id` **(many2one)** — Properties Base Definition 🔒 readonly → `properties.base.definition`
- `parent_id` **(many2one)** — Related Company → `res.partner`
- `child_ids` **(one2many)** — Contact → `res.partner`
- `user_id` **(many2one)** — Salesperson → `res.users`
  > The internal user in charge of this contact.
- `same_vat_partner_id` **(many2one)** — Partner with same Tax ID 🔒 readonly → `res.partner`
- `same_company_registry_partner_id` **(many2one)** — Partner with same Company Registry 🔒 readonly → `res.partner`
- `bank_ids` **(one2many)** — Banks → `res.partner.bank`
- `category_id` **(many2many)** — Tags → `res.partner.category`
- `state_id` **(many2one)** — State → `res.country.state`
- `country_id` **(many2one)** — Country → `res.country`
- `industry_id` **(many2one)** — Industry → `res.partner.industry`
- `user_ids` **(one2many)** — Users → `res.users`
- `main_user_id` **(many2one)** — Main User 🔒 readonly → `res.users`
  > There can be several users related to the same partner. When a single user is needed, this field attempts to find the most appropriate one.
- `commercial_partner_id` **(many2one)** — Commercial Entity 🔒 readonly → `res.partner`
- `self` **(many2one)** — Self 🔒 readonly → `res.partner`
- `channel_ids` **(many2many)** — Channels → `discuss.channel`
- `channel_member_ids` **(one2many)** — Channel Member → `discuss.channel.member`
- `rtc_session_ids` **(one2many)** — Rtc Session → `discuss.channel.rtc.session`
- `agent_ids` **(one2many)** — Agent → `ai.agent`
- `meeting_ids` **(many2many)** — Meetings → `calendar.event`
- `property_product_pricelist` **(many2one)** — Pricelist → `product.pricelist`
  > Used for sales to the current partner
- `specific_property_product_pricelist` **(many2one)** — Specific Property Product Pricelist → `product.pricelist`
- `city_id` **(many2one)** — City ID → `res.city`
- `upcoming_appointment_ids` **(many2many)** — Upcoming Appointments 🔒 readonly → `calendar.event`
- `payment_token_ids` **(one2many)** — Payment Tokens → `payment.token`
- `duplicate_bank_partner_ids` **(many2many)** — Duplicate Bank Partner 🔒 readonly → `res.partner`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `property_account_payable_id` **(many2one)** — Account Payable → `account.account`
- `property_account_receivable_id` **(many2one)** — Account Receivable → `account.account`
- `property_account_position_id` **(many2one)** — Fiscal Position → `account.fiscal.position`
  > The fiscal position determines the taxes/accounts used for this contact.
- `property_payment_term_id` **(many2one)** — Customer Payment Terms → `account.payment.term`
- `property_supplier_payment_term_id` **(many2one)** — Vendor Payment Terms → `account.payment.term`
- `ref_company_ids` **(one2many)** — Companies that refers to partner → `res.company`
- `invoice_ids` **(one2many)** — Invoices 🔒 readonly → `account.move`
- `contract_ids` **(one2many)** — Partner Contracts 🔒 readonly → `account.analytic.account`
- `invoice_template_pdf_report_id` **(many2one)** — Invoice report → `ir.actions.report`
- `available_invoice_template_pdf_report_ids` **(one2many)** — Available Invoice Template Pdf Report 🔒 readonly → `ir.actions.report`
- `property_outbound_payment_method_line_id` **(many2one)** — Property Outbound Payment Method Line → `account.payment.method.line`
- `property_inbound_payment_method_line_id` **(many2one)** — Property Inbound Payment Method Line → `account.payment.method.line`
- `opportunity_ids` **(one2many)** — Opportunities → `crm.lead`
- `document_ids` **(one2many)** — Documents → `documents.document`
- `sla_ids` **(many2many)** — SLA Policies → `helpdesk.sla`
  > SLA Policies that will automatically apply to the tickets submitted by this customer.
- `project_ids` **(one2many)** — Projects → `project.project`
- `property_stock_customer` **(many2one)** — Customer Location → `stock.location`
  > The stock location used as destination when sending goods to this contact.
- `property_stock_supplier` **(many2one)** — Vendor Location → `stock.location`
  > The stock location used as source when receiving goods from this contact.
- `visitor_ids` **(one2many)** — Visitors → `website.visitor`
- `applicant_ids` **(one2many)** — Applicants → `hr.applicant`
- `property_purchase_currency_id` **(many2one)** — Supplier Currency → `res.currency`
  > This currency will be used for purchases from the current partner
- `buyer_id` **(many2one)** — Buyer → `res.users`
- `account_represented_company_ids` **(one2many)** — Account Represented Company → `res.company`
- `l10n_latam_identification_type_id` **(many2one)** — Identification Type → `l10n_latam.identification.type`
  > The type of identification
- `property_stock_subcontractor` **(many2one)** — Subcontractor Location → `stock.location`
  > The stock location used as source and destination when sending        goods to this contact during a subcontracting process.
- `bom_ids` **(many2many)** — BoMs for which the Partner is one of the subcontractors 🔒 readonly → `mrp.bom`
- `production_ids` **(many2many)** — MRP Productions for which the Partner is the subcontractor 🔒 readonly → `mrp.production`
- `picking_ids` **(many2many)** — Stock Pickings for which the Partner is the subcontractor 🔒 readonly → `stock.picking`
- `purchase_line_ids` **(one2many)** — Purchase Lines → `purchase.order.line`
- `sale_order_ids` **(one2many)** — Sales Order → `sale.order`
- `unreconciled_aml_ids` **(one2many)** — Unreconciled Aml → `account.move.line`
- `unpaid_invoice_ids` **(one2many)** — Unpaid Invoice 🔒 readonly → `account.move`
- `property_delivery_carrier_id` **(many2one)** — Delivery Method → `delivery.carrier`
  > Used in sales orders.
- `wishlist_ids` **(one2many)** — Wishlist → `product.wishlist`

## Campos Calculados (readonly)

- `active_partner` **(boolean)** — Partner is Active 🔒 readonly
- `companies_count` **(integer)** — Number of Companies 🔒 readonly
- `tz_offset` **(char)** — Timezone offset 🔒 readonly
- `email_domain_placeholder` **(char)** — Email Domain Placeholder 🔒 readonly
- `accesses_count` **(integer)** — # Access Rights 🔒 readonly
  > Number of access rights that apply to the current user
- `rules_count` **(integer)** — # Record Rules 🔒 readonly
  > Number of record rules that apply to the current user
- `groups_count` **(integer)** — # Groups 🔒 readonly
  > Number of groups that apply to the current user
- `totp_enabled` **(boolean)** — Two-factor authentication 🔒 readonly
- `can_edit_role` **(boolean)** — Can Edit Role 🔒 readonly
- `is_out_of_office` **(boolean)** — Out of Office 🔒 readonly
- `im_status` **(char)** — IM Status 🔒 readonly
- `has_external_mail_server` **(boolean)** — Has External Mail Server 🔒 readonly
- `is_in_call` **(boolean)** — Is in call 🔒 readonly
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `new` (Invited), `active` (Confirmed)
- `gold_badge` **(integer)** — Gold badges count 🔒 readonly
- `silver_badge` **(integer)** — Silver badges count 🔒 readonly
- `bronze_badge` **(integer)** — Bronze badges count 🔒 readonly
- `job_title` **(char)** — Job Title 🔒 readonly
- `work_location_name` **(char)** — Work Location Name 🔒 readonly
- `work_location_type` **(selection)** — Work Location Type 🔒 readonly
  > Opções: `home` (Home), `office` (Office), `other` (Other)
- `employee_count` **(integer)** — Employee Count 🔒 readonly
- `is_system` **(boolean)** — Is System 🔒 readonly
- `is_hr_user` **(boolean)** — Is Hr User 🔒 readonly
- `is_seo_optimized` **(boolean)** — SEO optimized 🔒 readonly
- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
- `email_normalized` **(char)** — Normalized Email 🔒 readonly
  > This field is used to search on email address as the primary email field can contain more than strictly an email address.
- `is_blacklisted` **(boolean)** — Blacklist 🔒 readonly
  > If the email address is on the blacklist, the contact won't receive mass mailing anymore, from any list
- `image_1024` **(binary)** — Image 1024 🔒 readonly
- `image_512` **(binary)** — Image 512 🔒 readonly
- `image_256` **(binary)** — Image 256 🔒 readonly
- `image_128` **(binary)** — Image 128 🔒 readonly
- `avatar_1920` **(binary)** — Avatar 🔒 readonly
- `avatar_1024` **(binary)** — Avatar 1024 🔒 readonly
- `avatar_512` **(binary)** — Avatar 512 🔒 readonly
- `avatar_256` **(binary)** — Avatar 256 🔒 readonly
- `avatar_128` **(binary)** — Avatar 128 🔒 readonly
- `complete_name` **(char)** — Complete Name 🔒 readonly
- `parent_name` **(char)** — Parent name 🔒 readonly
- `active_lang_count` **(integer)** — Active Lang Count 🔒 readonly
- `vat_label` **(char)** — Tax ID Label 🔒 readonly
- `company_registry_label` **(char)** — Company ID Label 🔒 readonly
- `company_registry_placeholder` **(char)** — Company Registry Placeholder 🔒 readonly
- `type_address_label` **(char)** — Address Type Description 🔒 readonly
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `email_formatted` **(char)** — Formatted Email 🔒 readonly
  > Format email address "Name <email@domain>"
- `is_public` **(boolean)** — Is Public 🔒 readonly
- `partner_share` **(boolean)** — Share Partner 🔒 readonly
  > Either customer (not a user), either shared user. Indicated the current partner is a customer without access or with a limited access created for sharing data.
- `contact_address` **(char)** — Complete Address 🔒 readonly
- `commercial_company_name` **(char)** — Company Name Entity 🔒 readonly
- `application_statistics` **(json)** — Stats 🔒 readonly
- `contact_address_complete` **(char)** — Contact Address Complete 🔒 readonly
- `contact_address_inline` **(char)** — Inlined Complete Address 🔒 readonly
- `offline_since` **(datetime)** — Offline since 🔒 readonly
- `image_medium` **(binary)** — Medium-sized image 🔒 readonly
- `meeting_count` **(integer)** — # Meetings 🔒 readonly
- `phone_sanitized` **(char)** — Sanitized Number 🔒 readonly
  > Field used to store sanitized phone number. Helps speeding up searches and comparisons.
- `phone_sanitized_blacklisted` **(boolean)** — Phone Blacklisted 🔒 readonly
  > If the sanitized phone number is on the blacklist, the contact won't receive mass mailing sms anymore, from any list
- `phone_blacklisted` **(boolean)** — Blacklisted Phone is Phone 🔒 readonly
  > Indicates if a blacklisted sanitized phone number is a phone number. Helps distinguish which number is blacklisted             when there is both a mobile and phone field in a model.
- `country_enforce_cities` **(boolean)** — Enforce Cities 🔒 readonly
  > Check this box to ensure every address created in that country has a 'City' chosen in the list of the country's cities.
- `ocn_token` **(char)** — OCN Token 🔒 readonly
  > Used for sending notification to registered devices
- `certifications_count` **(integer)** — Certifications Count 🔒 readonly
- `certifications_company_count` **(integer)** — Company Certifications Count 🔒 readonly
- `wa_channel_count` **(integer)** — WhatsApp Channel Count 🔒 readonly
- `payment_token_count` **(integer)** — Payment Token Count 🔒 readonly
- `signature_count` **(integer)** — # Signatures 🔒 readonly
- `fiscal_country_codes` **(char)** — Fiscal Country Codes 🔒 readonly
- `fiscal_country_group_codes` **(json)** — Fiscal Country Group Codes 🔒 readonly
- `partner_vat_placeholder` **(char)** — Partner Vat Placeholder 🔒 readonly
- `partner_company_registry_placeholder` **(char)** — Partner Company Registry Placeholder 🔒 readonly
- `days_sales_outstanding` **(float)** — Days Sales Outstanding (DSO) 🔒 readonly
  > [(Total Receivable/Total Revenue) * number of days since the first invoice] for this customer
- `supplier_invoice_count` **(integer)** — # Vendor Bills 🔒 readonly
- `bank_account_count` **(integer)** — Bank 🔒 readonly
- `opportunity_count` **(integer)** — Opportunity Count 🔒 readonly
- `document_count` **(integer)** — Document Count 🔒 readonly
- `ticket_count` **(integer)** — Tickets 🔒 readonly
- `employees_count` **(integer)** — Employees Count 🔒 readonly
- `task_count` **(integer)** — # Tasks 🔒 readonly
- `is_ubl_format` **(boolean)** — Is Ubl Format 🔒 readonly
- `is_peppol_edi_format` **(boolean)** — Is Peppol Edi Format 🔒 readonly
- `available_peppol_eas` **(json)** — Available Peppol Eas 🔒 readonly
- `perform_vies_validation` **(boolean)** — Perform Vies Validation 🔒 readonly
- `loyalty_card_count` **(integer)** — Active loyalty cards 🔒 readonly
- `purchase_order_count` **(integer)** — Purchase Order Count 🔒 readonly
- `online_partner_information` **(char)** — Online Partner Information 🔒 readonly
- `is_vat` **(boolean)** — Is Vat 🔒 readonly
- `is_subcontractor` **(boolean)** — Subcontractor 🔒 readonly
- `on_time_rate` **(float)** — On-Time Delivery Rate 🔒 readonly
  > Over the past x days; the number of products received on time divided by the number of ordered products.x is either the System Parameter purchase_stock.on_time_delivery_days or the default 365
- `sale_order_count` **(integer)** — Sale Order Count 🔒 readonly
- `unpaid_invoices_count` **(integer)** — Unpaid Invoices Count 🔒 readonly
- `has_moves` **(boolean)** — Has Moves 🔒 readonly
