# Employee — `hr.employee`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `resource_id` **(many2one)** — Resource ⚠️ obrigatório → `resource.resource`
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `version_id` **(many2one)** — Version ⚠️ obrigatório 🔒 readonly → `hr.version`
- `version_ids` **(one2many)** — Employee Versions ⚠️ obrigatório → `hr.version`
- `date_version` **(date)** — Date Version ⚠️ obrigatório
- `last_modified_uid` **(many2one)** — Last Modified by ⚠️ obrigatório → `res.users`
- `last_modified_date` **(datetime)** — Last Modified on ⚠️ obrigatório
- `distance_home_work_unit` **(selection)** — Home-Work Distance unit ⚠️ obrigatório
  > Opções: `kilometers` (km), `miles` (mi)
- `marital` **(selection)** — Marital Status ⚠️ obrigatório
  > Opções: `single` (Single), `married` (Married), `cohabitant` (Legal Cohabitant), `widower` (Widower), `divorced` (Divorced)
- `employee_type` **(selection)** — Employee Type ⚠️ obrigatório
  > Opções: `employee` (Employee), `worker` (Worker), `student` (Student), `trainee` (Trainee), `contractor` (Contractor), `freelance` (Freelancer)
- `hr_responsible_id` **(many2one)** — HR Responsible ⚠️ obrigatório → `res.users`
  > Person responsible for validating the employee's contracts.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `image_1920` **(binary)** — Image
- `image_1024` **(binary)** — Image 1024 🔒 readonly
- `image_512` **(binary)** — Image 512 🔒 readonly
- `image_256` **(binary)** — Image 256 🔒 readonly
- `image_128` **(binary)** — Image 128 🔒 readonly
- `tz` **(selection)** — Timezone
  > This field is used in order to define in which timezone the resources will work.
  > Opções: `Africa/Abidjan` (Africa/Abidjan), `Africa/Accra` (Africa/Accra), `Africa/Addis_Ababa` (Africa/Addis_Ababa), `Africa/Algiers` (Africa/Algiers), `Africa/Asmara` (Africa/Asmara), `Africa/Asmera` (Africa/Asmera), `Africa/Bamako` (Africa/Bamako), `Africa/Bangui` (Africa/Bangui), `Africa/Banjul` (Africa/Banjul), `Africa/Bissau` (Africa/Bissau), `Africa/Blantyre` (Africa/Blantyre), `Africa/Brazzaville` (Africa/Brazzaville), `Africa/Bujumbura` (Africa/Bujumbura), `Africa/Cairo` (Africa/Cairo), `Africa/Casablanca` (Africa/Casablanca), `Africa/Ceuta` (Africa/Ceuta), `Africa/Conakry` (Africa/Conakry), `Africa/Dakar` (Africa/Dakar), `Africa/Dar_es_Salaam` (Africa/Dar_es_Salaam), `Africa/Djibouti` (Africa/Djibouti), `Africa/Douala` (Africa/Douala), `Africa/El_Aaiun` (Africa/El_Aaiun), `Africa/Freetown` (Africa/Freetown), `Africa/Gaborone` (Africa/Gaborone), `Africa/Harare` (Africa/Harare), `Africa/Johannesburg` (Africa/Johannesburg), `Africa/Juba` (Africa/Juba), `Africa/Kampala` (Africa/Kampala), `Africa/Khartoum` (Africa/Khartoum), `Africa/Kigali` (Africa/Kigali), `Africa/Kinshasa` (Africa/Kinshasa), `Africa/Lagos` (Africa/Lagos), `Africa/Libreville` (Africa/Libreville), `Africa/Lome` (Africa/Lome), `Africa/Luanda` (Africa/Luanda), `Africa/Lubumbashi` (Africa/Lubumbashi), `Africa/Lusaka` (Africa/Lusaka), `Africa/Malabo` (Africa/Malabo), `Africa/Maputo` (Africa/Maputo), `Africa/Maseru` (Africa/Maseru), `Africa/Mbabane` (Africa/Mbabane), `Africa/Mogadishu` (Africa/Mogadishu), `Africa/Monrovia` (Africa/Monrovia), `Africa/Nairobi` (Africa/Nairobi), `Africa/Ndjamena` (Africa/Ndjamena), `Africa/Niamey` (Africa/Niamey), `Africa/Nouakchott` (Africa/Nouakchott), `Africa/Ouagadougou` (Africa/Ouagadougou), `Africa/Porto-Novo` (Africa/Porto-Novo), `Africa/Sao_Tome` (Africa/Sao_Tome), `Africa/Timbuktu` (Africa/Timbuktu), `Africa/Tripoli` (Africa/Tripoli), `Africa/Tunis` (Africa/Tunis), `Africa/Windhoek` (Africa/Windhoek), `America/Adak` (America/Adak), `America/Anchorage` (America/Anchorage), `America/Anguilla` (America/Anguilla), `America/Antigua` (America/Antigua), `America/Araguaina` (America/Araguaina), `America/Argentina/Buenos_Aires` (America/Argentina/Buenos_Aires), `America/Argentina/Catamarca` (America/Argentina/Catamarca), `America/Argentina/ComodRivadavia` (America/Argentina/ComodRivadavia), `America/Argentina/Cordoba` (America/Argentina/Cordoba), `America/Argentina/Jujuy` (America/Argentina/Jujuy), `America/Argentina/La_Rioja` (America/Argentina/La_Rioja), `America/Argentina/Mendoza` (America/Argentina/Mendoza), `America/Argentina/Rio_Gallegos` (America/Argentina/Rio_Gallegos), `America/Argentina/Salta` (America/Argentina/Salta), `America/Argentina/San_Juan` (America/Argentina/San_Juan), `America/Argentina/San_Luis` (America/Argentina/San_Luis), `America/Argentina/Tucuman` (America/Argentina/Tucuman), `America/Argentina/Ushuaia` (America/Argentina/Ushuaia), `America/Aruba` (America/Aruba), `America/Asuncion` (America/Asuncion), `America/Atikokan` (America/Atikokan), `America/Atka` (America/Atka), `America/Bahia` (America/Bahia), `America/Bahia_Banderas` (America/Bahia_Banderas), `America/Barbados` (America/Barbados), `America/Belem` (America/Belem), `America/Belize` (America/Belize), `America/Blanc-Sablon` (America/Blanc-Sablon), `America/Boa_Vista` (America/Boa_Vista), `America/Bogota` (America/Bogota), `America/Boise` (America/Boise), `America/Buenos_Aires` (America/Buenos_Aires), `America/Cambridge_Bay` (America/Cambridge_Bay), `America/Campo_Grande` (America/Campo_Grande), `America/Cancun` (America/Cancun), `America/Caracas` (America/Caracas), `America/Catamarca` (America/Catamarca), `America/Cayenne` (America/Cayenne), `America/Cayman` (America/Cayman), `America/Chicago` (America/Chicago), `America/Chihuahua` (America/Chihuahua), `America/Ciudad_Juarez` (America/Ciudad_Juarez), `America/Coral_Harbour` (America/Coral_Harbour), `America/Cordoba` (America/Cordoba), `America/Costa_Rica` (America/Costa_Rica), `America/Coyhaique` (America/Coyhaique), `America/Creston` (America/Creston), `America/Cuiaba` (America/Cuiaba), `America/Curacao` (America/Curacao), `America/Danmarkshavn` (America/Danmarkshavn), `America/Dawson` (America/Dawson), `America/Dawson_Creek` (America/Dawson_Creek), `America/Denver` (America/Denver), `America/Detroit` (America/Detroit), `America/Dominica` (America/Dominica), `America/Edmonton` (America/Edmonton), `America/Eirunepe` (America/Eirunepe), `America/El_Salvador` (America/El_Salvador), `America/Ensenada` (America/Ensenada), `America/Fort_Nelson` (America/Fort_Nelson), `America/Fort_Wayne` (America/Fort_Wayne), `America/Fortaleza` (America/Fortaleza), `America/Glace_Bay` (America/Glace_Bay), `America/Godthab` (America/Godthab), `America/Goose_Bay` (America/Goose_Bay), `America/Grand_Turk` (America/Grand_Turk), `America/Grenada` (America/Grenada), `America/Guadeloupe` (America/Guadeloupe), `America/Guatemala` (America/Guatemala), `America/Guayaquil` (America/Guayaquil), `America/Guyana` (America/Guyana), `America/Halifax` (America/Halifax), `America/Havana` (America/Havana), `America/Hermosillo` (America/Hermosillo), `America/Indiana/Indianapolis` (America/Indiana/Indianapolis), `America/Indiana/Knox` (America/Indiana/Knox), `America/Indiana/Marengo` (America/Indiana/Marengo), `America/Indiana/Petersburg` (America/Indiana/Petersburg), `America/Indiana/Tell_City` (America/Indiana/Tell_City), `America/Indiana/Vevay` (America/Indiana/Vevay), `America/Indiana/Vincennes` (America/Indiana/Vincennes), `America/Indiana/Winamac` (America/Indiana/Winamac), `America/Indianapolis` (America/Indianapolis), `America/Inuvik` (America/Inuvik), `America/Iqaluit` (America/Iqaluit), `America/Jamaica` (America/Jamaica), `America/Jujuy` (America/Jujuy), `America/Juneau` (America/Juneau), `America/Kentucky/Louisville` (America/Kentucky/Louisville), `America/Kentucky/Monticello` (America/Kentucky/Monticello), `America/Knox_IN` (America/Knox_IN), `America/Kralendijk` (America/Kralendijk), `America/La_Paz` (America/La_Paz), `America/Lima` (America/Lima), `America/Los_Angeles` (America/Los_Angeles), `America/Louisville` (America/Louisville), `America/Lower_Princes` (America/Lower_Princes), `America/Maceio` (America/Maceio), `America/Managua` (America/Managua), `America/Manaus` (America/Manaus), `America/Marigot` (America/Marigot), `America/Martinique` (America/Martinique), `America/Matamoros` (America/Matamoros), `America/Mazatlan` (America/Mazatlan), `America/Mendoza` (America/Mendoza), `America/Menominee` (America/Menominee), `America/Merida` (America/Merida), `America/Metlakatla` (America/Metlakatla), `America/Mexico_City` (America/Mexico_City), `America/Miquelon` (America/Miquelon), `America/Moncton` (America/Moncton), `America/Monterrey` (America/Monterrey), `America/Montevideo` (America/Montevideo), `America/Montreal` (America/Montreal), `America/Montserrat` (America/Montserrat), `America/Nassau` (America/Nassau), `America/New_York` (America/New_York), `America/Nipigon` (America/Nipigon), `America/Nome` (America/Nome), `America/Noronha` (America/Noronha), `America/North_Dakota/Beulah` (America/North_Dakota/Beulah), `America/North_Dakota/Center` (America/North_Dakota/Center), `America/North_Dakota/New_Salem` (America/North_Dakota/New_Salem), `America/Nuuk` (America/Nuuk), `America/Ojinaga` (America/Ojinaga), `America/Panama` (America/Panama), `America/Pangnirtung` (America/Pangnirtung), `America/Paramaribo` (America/Paramaribo), `America/Phoenix` (America/Phoenix), `America/Port-au-Prince` (America/Port-au-Prince), `America/Port_of_Spain` (America/Port_of_Spain), `America/Porto_Acre` (America/Porto_Acre), `America/Porto_Velho` (America/Porto_Velho), `America/Puerto_Rico` (America/Puerto_Rico), `America/Punta_Arenas` (America/Punta_Arenas), `America/Rainy_River` (America/Rainy_River), `America/Rankin_Inlet` (America/Rankin_Inlet), `America/Recife` (America/Recife), `America/Regina` (America/Regina), `America/Resolute` (America/Resolute), `America/Rio_Branco` (America/Rio_Branco), `America/Rosario` (America/Rosario), `America/Santa_Isabel` (America/Santa_Isabel), `America/Santarem` (America/Santarem), `America/Santiago` (America/Santiago), `America/Santo_Domingo` (America/Santo_Domingo), `America/Sao_Paulo` (America/Sao_Paulo), `America/Scoresbysund` (America/Scoresbysund), `America/Shiprock` (America/Shiprock), `America/Sitka` (America/Sitka), `America/St_Barthelemy` (America/St_Barthelemy), `America/St_Johns` (America/St_Johns), `America/St_Kitts` (America/St_Kitts), `America/St_Lucia` (America/St_Lucia), `America/St_Thomas` (America/St_Thomas), `America/St_Vincent` (America/St_Vincent), `America/Swift_Current` (America/Swift_Current), `America/Tegucigalpa` (America/Tegucigalpa), `America/Thule` (America/Thule), `America/Thunder_Bay` (America/Thunder_Bay), `America/Tijuana` (America/Tijuana), `America/Toronto` (America/Toronto), `America/Tortola` (America/Tortola), `America/Vancouver` (America/Vancouver), `America/Virgin` (America/Virgin), `America/Whitehorse` (America/Whitehorse), `America/Winnipeg` (America/Winnipeg), `America/Yakutat` (America/Yakutat), `America/Yellowknife` (America/Yellowknife), `Antarctica/Casey` (Antarctica/Casey), `Antarctica/Davis` (Antarctica/Davis), `Antarctica/DumontDUrville` (Antarctica/DumontDUrville), `Antarctica/Macquarie` (Antarctica/Macquarie), `Antarctica/Mawson` (Antarctica/Mawson), `Antarctica/McMurdo` (Antarctica/McMurdo), `Antarctica/Palmer` (Antarctica/Palmer), `Antarctica/Rothera` (Antarctica/Rothera), `Antarctica/South_Pole` (Antarctica/South_Pole), `Antarctica/Syowa` (Antarctica/Syowa), `Antarctica/Troll` (Antarctica/Troll), `Antarctica/Vostok` (Antarctica/Vostok), `Arctic/Longyearbyen` (Arctic/Longyearbyen), `Asia/Aden` (Asia/Aden), `Asia/Almaty` (Asia/Almaty), `Asia/Amman` (Asia/Amman), `Asia/Anadyr` (Asia/Anadyr), `Asia/Aqtau` (Asia/Aqtau), `Asia/Aqtobe` (Asia/Aqtobe), `Asia/Ashgabat` (Asia/Ashgabat), `Asia/Ashkhabad` (Asia/Ashkhabad), `Asia/Atyrau` (Asia/Atyrau), `Asia/Baghdad` (Asia/Baghdad), `Asia/Bahrain` (Asia/Bahrain), `Asia/Baku` (Asia/Baku), `Asia/Bangkok` (Asia/Bangkok), `Asia/Barnaul` (Asia/Barnaul), `Asia/Beirut` (Asia/Beirut), `Asia/Bishkek` (Asia/Bishkek), `Asia/Brunei` (Asia/Brunei), `Asia/Calcutta` (Asia/Calcutta), `Asia/Chita` (Asia/Chita), `Asia/Choibalsan` (Asia/Choibalsan), `Asia/Chongqing` (Asia/Chongqing), `Asia/Chungking` (Asia/Chungking), `Asia/Colombo` (Asia/Colombo), `Asia/Dacca` (Asia/Dacca), `Asia/Damascus` (Asia/Damascus), `Asia/Dhaka` (Asia/Dhaka), `Asia/Dili` (Asia/Dili), `Asia/Dubai` (Asia/Dubai), `Asia/Dushanbe` (Asia/Dushanbe), `Asia/Famagusta` (Asia/Famagusta), `Asia/Gaza` (Asia/Gaza), `Asia/Harbin` (Asia/Harbin), `Asia/Hebron` (Asia/Hebron), `Asia/Ho_Chi_Minh` (Asia/Ho_Chi_Minh), `Asia/Hong_Kong` (Asia/Hong_Kong), `Asia/Hovd` (Asia/Hovd), `Asia/Irkutsk` (Asia/Irkutsk), `Asia/Istanbul` (Asia/Istanbul), `Asia/Jakarta` (Asia/Jakarta), `Asia/Jayapura` (Asia/Jayapura), `Asia/Jerusalem` (Asia/Jerusalem), `Asia/Kabul` (Asia/Kabul), `Asia/Kamchatka` (Asia/Kamchatka), `Asia/Karachi` (Asia/Karachi), `Asia/Kashgar` (Asia/Kashgar), `Asia/Kathmandu` (Asia/Kathmandu), `Asia/Katmandu` (Asia/Katmandu), `Asia/Khandyga` (Asia/Khandyga), `Asia/Kolkata` (Asia/Kolkata), `Asia/Krasnoyarsk` (Asia/Krasnoyarsk), `Asia/Kuala_Lumpur` (Asia/Kuala_Lumpur), `Asia/Kuching` (Asia/Kuching), `Asia/Kuwait` (Asia/Kuwait), `Asia/Macao` (Asia/Macao), `Asia/Macau` (Asia/Macau), `Asia/Magadan` (Asia/Magadan), `Asia/Makassar` (Asia/Makassar), `Asia/Manila` (Asia/Manila), `Asia/Muscat` (Asia/Muscat), `Asia/Nicosia` (Asia/Nicosia), `Asia/Novokuznetsk` (Asia/Novokuznetsk), `Asia/Novosibirsk` (Asia/Novosibirsk), `Asia/Omsk` (Asia/Omsk), `Asia/Oral` (Asia/Oral), `Asia/Phnom_Penh` (Asia/Phnom_Penh), `Asia/Pontianak` (Asia/Pontianak), `Asia/Pyongyang` (Asia/Pyongyang), `Asia/Qatar` (Asia/Qatar), `Asia/Qostanay` (Asia/Qostanay), `Asia/Qyzylorda` (Asia/Qyzylorda), `Asia/Rangoon` (Asia/Rangoon), `Asia/Riyadh` (Asia/Riyadh), `Asia/Saigon` (Asia/Saigon), `Asia/Sakhalin` (Asia/Sakhalin), `Asia/Samarkand` (Asia/Samarkand), `Asia/Seoul` (Asia/Seoul), `Asia/Shanghai` (Asia/Shanghai), `Asia/Singapore` (Asia/Singapore), `Asia/Srednekolymsk` (Asia/Srednekolymsk), `Asia/Taipei` (Asia/Taipei), `Asia/Tashkent` (Asia/Tashkent), `Asia/Tbilisi` (Asia/Tbilisi), `Asia/Tehran` (Asia/Tehran), `Asia/Tel_Aviv` (Asia/Tel_Aviv), `Asia/Thimbu` (Asia/Thimbu), `Asia/Thimphu` (Asia/Thimphu), `Asia/Tokyo` (Asia/Tokyo), `Asia/Tomsk` (Asia/Tomsk), `Asia/Ujung_Pandang` (Asia/Ujung_Pandang), `Asia/Ulaanbaatar` (Asia/Ulaanbaatar), `Asia/Ulan_Bator` (Asia/Ulan_Bator), `Asia/Urumqi` (Asia/Urumqi), `Asia/Ust-Nera` (Asia/Ust-Nera), `Asia/Vientiane` (Asia/Vientiane), `Asia/Vladivostok` (Asia/Vladivostok), `Asia/Yakutsk` (Asia/Yakutsk), `Asia/Yangon` (Asia/Yangon), `Asia/Yekaterinburg` (Asia/Yekaterinburg), `Asia/Yerevan` (Asia/Yerevan), `Atlantic/Azores` (Atlantic/Azores), `Atlantic/Bermuda` (Atlantic/Bermuda), `Atlantic/Canary` (Atlantic/Canary), `Atlantic/Cape_Verde` (Atlantic/Cape_Verde), `Atlantic/Faeroe` (Atlantic/Faeroe), `Atlantic/Faroe` (Atlantic/Faroe), `Atlantic/Jan_Mayen` (Atlantic/Jan_Mayen), `Atlantic/Madeira` (Atlantic/Madeira), `Atlantic/Reykjavik` (Atlantic/Reykjavik), `Atlantic/South_Georgia` (Atlantic/South_Georgia), `Atlantic/St_Helena` (Atlantic/St_Helena), `Atlantic/Stanley` (Atlantic/Stanley), `Australia/ACT` (Australia/ACT), `Australia/Adelaide` (Australia/Adelaide), `Australia/Brisbane` (Australia/Brisbane), `Australia/Broken_Hill` (Australia/Broken_Hill), `Australia/Canberra` (Australia/Canberra), `Australia/Currie` (Australia/Currie), `Australia/Darwin` (Australia/Darwin), `Australia/Eucla` (Australia/Eucla), `Australia/Hobart` (Australia/Hobart), `Australia/LHI` (Australia/LHI), `Australia/Lindeman` (Australia/Lindeman), `Australia/Lord_Howe` (Australia/Lord_Howe), `Australia/Melbourne` (Australia/Melbourne), `Australia/NSW` (Australia/NSW), `Australia/North` (Australia/North), `Australia/Perth` (Australia/Perth), `Australia/Queensland` (Australia/Queensland), `Australia/South` (Australia/South), `Australia/Sydney` (Australia/Sydney), `Australia/Tasmania` (Australia/Tasmania), `Australia/Victoria` (Australia/Victoria), `Australia/West` (Australia/West), `Australia/Yancowinna` (Australia/Yancowinna), `Brazil/Acre` (Brazil/Acre), `Brazil/DeNoronha` (Brazil/DeNoronha), `Brazil/East` (Brazil/East), `Brazil/West` (Brazil/West), `CET` (CET), `CST6CDT` (CST6CDT), `Canada/Atlantic` (Canada/Atlantic), `Canada/Central` (Canada/Central), `Canada/Eastern` (Canada/Eastern), `Canada/Mountain` (Canada/Mountain), `Canada/Newfoundland` (Canada/Newfoundland), `Canada/Pacific` (Canada/Pacific), `Canada/Saskatchewan` (Canada/Saskatchewan), `Canada/Yukon` (Canada/Yukon), `Chile/Continental` (Chile/Continental), `Chile/EasterIsland` (Chile/EasterIsland), `Cuba` (Cuba), `EET` (EET), `EST` (EST), `EST5EDT` (EST5EDT), `Egypt` (Egypt), `Eire` (Eire), `Europe/Amsterdam` (Europe/Amsterdam), `Europe/Andorra` (Europe/Andorra), `Europe/Astrakhan` (Europe/Astrakhan), `Europe/Athens` (Europe/Athens), `Europe/Belfast` (Europe/Belfast), `Europe/Belgrade` (Europe/Belgrade), `Europe/Berlin` (Europe/Berlin), `Europe/Bratislava` (Europe/Bratislava), `Europe/Brussels` (Europe/Brussels), `Europe/Bucharest` (Europe/Bucharest), `Europe/Budapest` (Europe/Budapest), `Europe/Busingen` (Europe/Busingen), `Europe/Chisinau` (Europe/Chisinau), `Europe/Copenhagen` (Europe/Copenhagen), `Europe/Dublin` (Europe/Dublin), `Europe/Gibraltar` (Europe/Gibraltar), `Europe/Guernsey` (Europe/Guernsey), `Europe/Helsinki` (Europe/Helsinki), `Europe/Isle_of_Man` (Europe/Isle_of_Man), `Europe/Istanbul` (Europe/Istanbul), `Europe/Jersey` (Europe/Jersey), `Europe/Kaliningrad` (Europe/Kaliningrad), `Europe/Kiev` (Europe/Kiev), `Europe/Kirov` (Europe/Kirov), `Europe/Kyiv` (Europe/Kyiv), `Europe/Lisbon` (Europe/Lisbon), `Europe/Ljubljana` (Europe/Ljubljana), `Europe/London` (Europe/London), `Europe/Luxembourg` (Europe/Luxembourg), `Europe/Madrid` (Europe/Madrid), `Europe/Malta` (Europe/Malta), `Europe/Mariehamn` (Europe/Mariehamn), `Europe/Minsk` (Europe/Minsk), `Europe/Monaco` (Europe/Monaco), `Europe/Moscow` (Europe/Moscow), `Europe/Nicosia` (Europe/Nicosia), `Europe/Oslo` (Europe/Oslo), `Europe/Paris` (Europe/Paris), `Europe/Podgorica` (Europe/Podgorica), `Europe/Prague` (Europe/Prague), `Europe/Riga` (Europe/Riga), `Europe/Rome` (Europe/Rome), `Europe/Samara` (Europe/Samara), `Europe/San_Marino` (Europe/San_Marino), `Europe/Sarajevo` (Europe/Sarajevo), `Europe/Saratov` (Europe/Saratov), `Europe/Simferopol` (Europe/Simferopol), `Europe/Skopje` (Europe/Skopje), `Europe/Sofia` (Europe/Sofia), `Europe/Stockholm` (Europe/Stockholm), `Europe/Tallinn` (Europe/Tallinn), `Europe/Tirane` (Europe/Tirane), `Europe/Tiraspol` (Europe/Tiraspol), `Europe/Ulyanovsk` (Europe/Ulyanovsk), `Europe/Uzhgorod` (Europe/Uzhgorod), `Europe/Vaduz` (Europe/Vaduz), `Europe/Vatican` (Europe/Vatican), `Europe/Vienna` (Europe/Vienna), `Europe/Vilnius` (Europe/Vilnius), `Europe/Volgograd` (Europe/Volgograd), `Europe/Warsaw` (Europe/Warsaw), `Europe/Zagreb` (Europe/Zagreb), `Europe/Zaporozhye` (Europe/Zaporozhye), `Europe/Zurich` (Europe/Zurich), `GB` (GB), `GB-Eire` (GB-Eire), `GMT` (GMT), `GMT+0` (GMT+0), `GMT-0` (GMT-0), `GMT0` (GMT0), `Greenwich` (Greenwich), `HST` (HST), `Hongkong` (Hongkong), `Iceland` (Iceland), `Indian/Antananarivo` (Indian/Antananarivo), `Indian/Chagos` (Indian/Chagos), `Indian/Christmas` (Indian/Christmas), `Indian/Cocos` (Indian/Cocos), `Indian/Comoro` (Indian/Comoro), `Indian/Kerguelen` (Indian/Kerguelen), `Indian/Mahe` (Indian/Mahe), `Indian/Maldives` (Indian/Maldives), `Indian/Mauritius` (Indian/Mauritius), `Indian/Mayotte` (Indian/Mayotte), `Indian/Reunion` (Indian/Reunion), `Iran` (Iran), `Israel` (Israel), `Jamaica` (Jamaica), `Japan` (Japan), `Kwajalein` (Kwajalein), `Libya` (Libya), `MET` (MET), `MST` (MST), `MST7MDT` (MST7MDT), `Mexico/BajaNorte` (Mexico/BajaNorte), `Mexico/BajaSur` (Mexico/BajaSur), `Mexico/General` (Mexico/General), `NZ` (NZ), `NZ-CHAT` (NZ-CHAT), `Navajo` (Navajo), `PRC` (PRC), `PST8PDT` (PST8PDT), `Pacific/Apia` (Pacific/Apia), `Pacific/Auckland` (Pacific/Auckland), `Pacific/Bougainville` (Pacific/Bougainville), `Pacific/Chatham` (Pacific/Chatham), `Pacific/Chuuk` (Pacific/Chuuk), `Pacific/Easter` (Pacific/Easter), `Pacific/Efate` (Pacific/Efate), `Pacific/Enderbury` (Pacific/Enderbury), `Pacific/Fakaofo` (Pacific/Fakaofo), `Pacific/Fiji` (Pacific/Fiji), `Pacific/Funafuti` (Pacific/Funafuti), `Pacific/Galapagos` (Pacific/Galapagos), `Pacific/Gambier` (Pacific/Gambier), `Pacific/Guadalcanal` (Pacific/Guadalcanal), `Pacific/Guam` (Pacific/Guam), `Pacific/Honolulu` (Pacific/Honolulu), `Pacific/Johnston` (Pacific/Johnston), `Pacific/Kanton` (Pacific/Kanton), `Pacific/Kiritimati` (Pacific/Kiritimati), `Pacific/Kosrae` (Pacific/Kosrae), `Pacific/Kwajalein` (Pacific/Kwajalein), `Pacific/Majuro` (Pacific/Majuro), `Pacific/Marquesas` (Pacific/Marquesas), `Pacific/Midway` (Pacific/Midway), `Pacific/Nauru` (Pacific/Nauru), `Pacific/Niue` (Pacific/Niue), `Pacific/Norfolk` (Pacific/Norfolk), `Pacific/Noumea` (Pacific/Noumea), `Pacific/Pago_Pago` (Pacific/Pago_Pago), `Pacific/Palau` (Pacific/Palau), `Pacific/Pitcairn` (Pacific/Pitcairn), `Pacific/Pohnpei` (Pacific/Pohnpei), `Pacific/Ponape` (Pacific/Ponape), `Pacific/Port_Moresby` (Pacific/Port_Moresby), `Pacific/Rarotonga` (Pacific/Rarotonga), `Pacific/Saipan` (Pacific/Saipan), `Pacific/Samoa` (Pacific/Samoa), `Pacific/Tahiti` (Pacific/Tahiti), `Pacific/Tarawa` (Pacific/Tarawa), `Pacific/Tongatapu` (Pacific/Tongatapu), `Pacific/Truk` (Pacific/Truk), `Pacific/Wake` (Pacific/Wake), `Pacific/Wallis` (Pacific/Wallis), `Pacific/Yap` (Pacific/Yap), `Poland` (Poland), `Portugal` (Portugal), `ROC` (ROC), `ROK` (ROK), `Singapore` (Singapore), `Turkey` (Turkey), `UCT` (UCT), `US/Alaska` (US/Alaska), `US/Aleutian` (US/Aleutian), `US/Arizona` (US/Arizona), `US/Central` (US/Central), `US/East-Indiana` (US/East-Indiana), `US/Eastern` (US/Eastern), `US/Hawaii` (US/Hawaii), `US/Indiana-Starke` (US/Indiana-Starke), `US/Michigan` (US/Michigan), `US/Mountain` (US/Mountain), `US/Pacific` (US/Pacific), `US/Samoa` (US/Samoa), `UTC` (UTC), `Universal` (Universal), `W-SU` (W-SU), `WET` (WET), `Zulu` (Zulu), `Etc/GMT` (Etc/GMT), `Etc/GMT+0` (Etc/GMT+0), `Etc/GMT+1` (Etc/GMT+1), `Etc/GMT+10` (Etc/GMT+10), `Etc/GMT+11` (Etc/GMT+11), `Etc/GMT+12` (Etc/GMT+12), `Etc/GMT+2` (Etc/GMT+2), `Etc/GMT+3` (Etc/GMT+3), `Etc/GMT+4` (Etc/GMT+4), `Etc/GMT+5` (Etc/GMT+5), `Etc/GMT+6` (Etc/GMT+6), `Etc/GMT+7` (Etc/GMT+7), `Etc/GMT+8` (Etc/GMT+8), `Etc/GMT+9` (Etc/GMT+9), `Etc/GMT-0` (Etc/GMT-0), `Etc/GMT-1` (Etc/GMT-1), `Etc/GMT-10` (Etc/GMT-10), `Etc/GMT-11` (Etc/GMT-11), `Etc/GMT-12` (Etc/GMT-12), `Etc/GMT-13` (Etc/GMT-13), `Etc/GMT-14` (Etc/GMT-14), `Etc/GMT-2` (Etc/GMT-2), `Etc/GMT-3` (Etc/GMT-3), `Etc/GMT-4` (Etc/GMT-4), `Etc/GMT-5` (Etc/GMT-5), `Etc/GMT-6` (Etc/GMT-6), `Etc/GMT-7` (Etc/GMT-7), `Etc/GMT-8` (Etc/GMT-8), `Etc/GMT-9` (Etc/GMT-9), `Etc/GMT0` (Etc/GMT0), `Etc/Greenwich` (Etc/Greenwich), `Etc/UCT` (Etc/UCT), `Etc/UTC` (Etc/UTC), `Etc/Universal` (Etc/Universal), `Etc/Zulu` (Etc/Zulu)
- `name` **(char)** — Employee Name
- `active` **(boolean)** — Active
  > If the active field is set to False, it will allow you to hide the resource record without removing it.
- `work_phone` **(char)** — Work Phone
- `mobile_phone` **(char)** — Work Mobile
- `work_email` **(char)** — Work Email
- `legal_name` **(char)** — Legal Name
- `private_phone` **(char)** — Private Phone
- `private_email` **(char)** — Private Email
- `lang` **(selection)** — Lang
  > Opções: `en_US` (English (US)), `pt_BR` (Portuguese (BR) / Português (BR))
- `place_of_birth` **(char)** — Place of Birth
- `birthday` **(date)** — Birthday
- `birthday_public_display` **(boolean)** — Show to all employees
- `salary_distribution` **(json)** — Salary Distribution
- `permit_no` **(char)** — Work Permit No
- `visa_no` **(char)** — Visa No
- `visa_expire` **(date)** — Visa Expiration Date
- `work_permit_expiration_date` **(date)** — Work Permit Expiration Date
- `has_work_permit` **(binary)** — Work Permit
- `work_permit_scheduled_activity` **(boolean)** — Work Permit Scheduled Activity
- `certificate` **(selection)** — Certificate Level
  > Opções: `graduate` (Graduate), `bachelor` (Bachelor), `master` (Master), `doctor` (Doctor), `other` (Other)
- `study_field` **(char)** — Field of Study
- `study_school` **(char)** — School
- `emergency_contact` **(char)** — Emergency Contact
- `emergency_phone` **(char)** — Emergency Phone
- `color` **(integer)** — Color Index
- `barcode` **(char)** — Badge ID
  > ID used for employee identification.
- `pin` **(char)** — PIN
  > PIN used to Check In/Out in the Kiosk Mode of the Attendance application (if enabled in Configuration) and to change the cashier in the Point of Sale application.
- `id_card` **(binary)** — ID Card Copy
- `driving_license` **(binary)** — Driving License
- `private_car_plate` **(char)** — Private Car Plate
  > If you have more than one car, just separate the plates by a space.
- `employee_properties` **(properties)** — Properties
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `last_check_in` **(datetime)** — Check In 🔒 readonly
- `last_check_out` **(datetime)** — Check Out 🔒 readonly
- `filter_for_expense` **(boolean)** — Filter For Expense
- `today_location_name` **(char)** — Today Location Name
- `hourly_cost` **(monetary)** — Hourly Cost
- `next_appraisal_date` **(date)** — Next Appraisal Date
  > The date of the next appraisal is computed by the appraisal plan's dates (first appraisal + periodicity).
- `ongoing_appraisal_count` **(integer)** — Ongoing Appraisal Count 🔒 readonly
- `appraisal_count` **(integer)** — Appraisal Count 🔒 readonly
- `employee_token` **(char)** — Security Token 🔒 readonly
- `last_validated_timesheet_date` **(date)** — Last Validated Timesheet Date
- `billable_time_target` **(float)** — Billing Time Target
- `identification_id` **(char)** — Identification No
  > Enter the employee's National Identification Number issued by the government (e.g., Aadhaar, SIN, NIN). This is used for official records and statutory compliance.
- `ssnid` **(char)** — SSN No
  > Social Security Number
- `passport_id` **(char)** — Passport No
- `passport_expiration_date` **(date)** — Passport Expiration Date
- `sex` **(selection)** — Gender
  > This is the legal sex recognized by the state.
  > Opções: `male` (Male), `female` (Female), `other` (Other)
- `private_street` **(char)** — Private Street
- `private_street2` **(char)** — Private Street2
- `private_city` **(char)** — Private City
- `private_zip` **(char)** — Private Zip
- `distance_home_work` **(integer)** — Home-Work Distance
- `km_home_work` **(integer)** — Home-Work Distance in Km
- `spouse_complete_name` **(char)** — Spouse Legal Name
- `spouse_birthdate` **(date)** — Spouse Birthdate
- `children` **(integer)** — Dependent Children
- `job_title` **(char)** — Job Title
- `departure_description` **(html)** — Additional Information
- `departure_date` **(date)** — Departure Date
- `additional_note` **(text)** — Additional Note

## Relacionamentos

- `resource_calendar_id` **(many2one)** — Working Hours → `resource.calendar`
- `message_main_attachment_id` **(many2one)** — Main Attachment → `ir.attachment`
- `current_version_id` **(many2one)** — Current Version 🔒 readonly → `hr.version`
- `user_id` **(many2one)** — User → `res.users`
  > Related user name for the resource to manage its access.
- `user_partner_id` **(many2one)** — User's partner 🔒 readonly → `res.partner`
  > Partner-related data of the user
- `company_country_id` **(many2one)** — Company Country 🔒 readonly → `res.country`
- `work_contact_id` **(many2one)** — Work Contact → `res.partner`
- `country_of_birth` **(many2one)** — Country of Birth → `res.country`
- `bank_account_ids` **(many2many)** — Bank Accounts → `res.partner.bank`
  > Employee bank accounts to pay salaries
- `primary_bank_account_id` **(many2one)** — Primary Bank Account 🔒 readonly → `res.partner.bank`
- `parent_id` **(many2one)** — Manager → `hr.employee`
- `child_ids` **(one2many)** — Direct subordinates → `hr.employee`
- `coach_id` **(many2one)** — Coach → `hr.employee`
  > Select the "Employee" who is the coach of this employee. The "Coach" has no specific rights or responsibilities by default.
- `category_ids` **(many2many)** — Tags → `hr.employee.category`
- `currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
- `hr_employee_folder_id` **(many2one)** — HR Employee Folder → `documents.document`
- `hr_employee_contract_folder_id` **(many2one)** — HR Employee Contract Folder → `documents.document`
- `attendance_ids` **(one2many)** — Attendance → `hr.attendance`
- `last_attendance_id` **(many2one)** — Last Attendance 🔒 readonly → `hr.attendance`
- `overtime_ids` **(one2many)** — Overtime → `hr.attendance.overtime.line`
- `expense_manager_id` **(many2one)** — Expense Approver → `res.users`
  > Select the user responsible for approving "Expenses" of this employee. If empty, the approval is done by an Administrator or Approver (determined in settings/users).
- `goal_ids` **(one2many)** — Employee HR Goals 🔒 readonly → `gamification.goal`
- `badge_ids` **(one2many)** — Employee Badges 🔒 readonly → `gamification.badge.user`
  > All employee badges, linked to the employee either directly or through the user
- `direct_badge_ids` **(one2many)** — Direct Badge → `gamification.badge.user`
  > Badges directly linked to the employee
- `monday_location_id` **(many2one)** — Monday → `hr.work.location`
- `tuesday_location_id` **(many2one)** — Tuesday → `hr.work.location`
- `wednesday_location_id` **(many2one)** — Wednesday → `hr.work.location`
- `thursday_location_id` **(many2one)** — Thursday → `hr.work.location`
- `friday_location_id` **(many2one)** — Friday → `hr.work.location`
- `saturday_location_id` **(many2one)** — Saturday → `hr.work.location`
- `sunday_location_id` **(many2one)** — Sunday → `hr.work.location`
- `exceptional_location_id` **(many2one)** — Current 🔒 readonly → `hr.work.location`
  > This is the exceptional, non-weekly, location set for today.
- `subordinate_ids` **(one2many)** — Subordinates 🔒 readonly → `hr.employee`
  > Direct and indirect subordinates
- `applicant_ids` **(one2many)** — Applicants → `hr.applicant`
- `sign_request_ids` **(many2many)** — Requested Signatures → `sign.request`
- `resume_line_ids` **(one2many)** — Resume lines → `hr.resume.line`
- `employee_skill_ids` **(one2many)** — Skills → `hr.employee.skill`
- `current_employee_skill_ids` **(one2many)** — Current Employee Skill → `hr.employee.skill`
- `skill_ids` **(many2many)** — Skill 🔒 readonly → `hr.skill`
- `certification_ids` **(one2many)** — Certification → `hr.employee.skill`
- `related_partner_id` **(many2one)** — Related Partner 🔒 readonly → `res.partner`
- `appraisal_ids` **(one2many)** — Appraisal → `hr.appraisal`
- `goals_ids` **(many2many)** — Goals → `hr.appraisal.goal`
- `parent_user_id` **(many2one)** — Parent User 🔒 readonly → `res.users`
  > Related user name for the resource to manage its access.
- `last_appraisal_id` **(many2one)** — Last Appraisal → `hr.appraisal`
- `default_planning_role_id` **(many2one)** — Default Role → `planning.role`
  > Role that will be selected by default when creating a shift for this employee. This role will also have precedence over the other roles of the employee when planning orders.
- `planning_role_ids` **(many2many)** — Roles → `planning.role`
  > Roles that the employee can fill in. When creating a shift for this employee, only the shift templates for these roles will be displayed. Similarly, only the open shifts available for these roles will be sent to the employee when the schedule is published. Additionally, the employee will only be assigned orders for these roles (with the default planning role having precedence over the other ones). Leave empty for the employee to be assigned shifts regardless of the role.
- `timesheet_manager_id` **(many2one)** — Timesheet Approver → `res.users`
  > Select the user responsible for approving "Timesheet" of this employee. If empty, the approval is done by a Timesheets > Administrator or a Timesheets > User: all timesheets (as determined in the users settings).
- `employee_id` **(many2one)** — Employee → `hr.employee`
- `country_id` **(many2one)** — Nationality (Country) → `res.country`
- `allowed_country_state_ids` **(many2many)** — Allowed Country State 🔒 readonly → `res.country.state`
- `private_state_id` **(many2one)** — Private State → `res.country.state`
- `private_country_id` **(many2one)** — Private Country → `res.country`
- `department_id` **(many2one)** — Department → `hr.department`
- `job_id` **(many2one)** — Job → `hr.job`
- `address_id` **(many2one)** — Work Address → `res.partner`
- `work_location_id` **(many2one)** — Work Location → `hr.work.location`
- `departure_reason_id` **(many2one)** — Departure Reason → `hr.departure.reason`
- `contract_template_id` **(many2one)** — Contract Template → `hr.version`
  > Select a contract template to auto-fill the contract form with predefined values. You can still edit the fields as needed after applying the template.

## Campos Calculados (readonly)

- `avatar_1920` **(binary)** — Avatar 🔒 readonly
- `avatar_1024` **(binary)** — Avatar 1024 🔒 readonly
- `avatar_512` **(binary)** — Avatar 512 🔒 readonly
- `avatar_256` **(binary)** — Avatar 256 🔒 readonly
- `avatar_128` **(binary)** — Avatar 128 🔒 readonly
- `current_date_version` **(date)** — Current Date Version 🔒 readonly
- `versions_count` **(integer)** — Versions Count 🔒 readonly
- `share` **(boolean)** — Share User 🔒 readonly
  > External user with limited access, created only for the purpose of sharing data.
- `phone` **(char)** — Phone 🔒 readonly
- `im_status` **(char)** — IM Status 🔒 readonly
- `email` **(char)** — Email 🔒 readonly
- `hr_presence_state` **(selection)** — Hr Presence State 🔒 readonly
  > Opções: `present` (Present), `absent` (Absent), `archive` (Archived), `out_of_working_hour` (Off-Hours)
- `last_activity` **(date)** — Last Activity 🔒 readonly
- `last_activity_time` **(char)** — Last Activity Time 🔒 readonly
- `hr_icon_display` **(selection)** — Hr Icon Display 🔒 readonly
  > Opções: `presence_present` (Present), `presence_out_of_working_hour` (Off-Hours), `presence_absent` (Absent), `presence_archive` (Archived), `presence_undetermined` (Undetermined), `presence_home` (At Home), `presence_office` (At Office), `presence_other` (At Other)
- `show_hr_icon_display` **(boolean)** — Show Hr Icon Display 🔒 readonly
- `newly_hired` **(boolean)** — Newly Hired 🔒 readonly
- `company_country_code` **(char)** — Company Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
- `is_user_active` **(boolean)** — User's active 🔒 readonly
- `birthday_public_display_string` **(char)** — Public Date of Birth 🔒 readonly
- `is_trusted_bank_account` **(boolean)** — Is Trusted Bank Account 🔒 readonly
- `has_multiple_bank_accounts` **(boolean)** — Has Multiple Bank Accounts 🔒 readonly
- `work_permit_name` **(char)** — work_permit_name 🔒 readonly
- `work_location_name` **(char)** — Work Location Name 🔒 readonly
- `work_location_type` **(selection)** — Work Location Type 🔒 readonly
  > Opções: `home` (Home), `office` (Office), `other` (Other)
- `related_partners_count` **(integer)** — Related Partners Count 🔒 readonly
- `document_count` **(integer)** — Document Count 🔒 readonly
- `attendance_state` **(selection)** — Attendance Status 🔒 readonly
  > Opções: `checked_out` (Checked out), `checked_in` (Checked in)
- `hours_last_month` **(float)** — Hours Last Month 🔒 readonly
- `hours_last_month_overtime` **(float)** — Hours Last Month Overtime 🔒 readonly
- `hours_today` **(float)** — Hours Today 🔒 readonly
- `hours_previously_today` **(float)** — Hours Previously Today 🔒 readonly
- `last_attendance_worked_hours` **(float)** — Last Attendance Worked Hours 🔒 readonly
- `hours_last_month_display` **(char)** — Hours Last Month Display 🔒 readonly
- `total_overtime` **(float)** — Total Overtime 🔒 readonly
- `display_extra_hours` **(boolean)** — Display Extra Hours 🔒 readonly
- `has_badges` **(boolean)** — Has Badges 🔒 readonly
- `child_all_count` **(integer)** — Indirect Subordinates Count 🔒 readonly
- `department_color` **(integer)** — Department Color 🔒 readonly
- `child_count` **(integer)** — Direct Subordinates Count 🔒 readonly
- `is_subordinate` **(boolean)** — Is Subordinate 🔒 readonly
- `display_certification_page` **(boolean)** — Display Certification Page 🔒 readonly
- `last_ongoing_appraisal_date` **(date)** — Last Ongoing Appraisal Date 🔒 readonly
- `is_last_appraisal_late` **(boolean)** — Is Last Appraisal Late 🔒 readonly
- `uncomplete_goals_count` **(integer)** — Uncomplete Goals Count 🔒 readonly
- `goals_count` **(integer)** — Goals Count 🔒 readonly
- `can_request_appraisal` **(boolean)** — Can Request Appraisal 🔒 readonly
- `last_appraisal_state` **(selection)** — Status 🔒 readonly
  > Opções: `1_new` (Draft), `2_pending` (Ongoing), `3_done` (Done)
- `has_timesheet` **(boolean)** — Has Timesheet 🔒 readonly
- `has_slots` **(boolean)** — Has Slots 🔒 readonly
- `has_subscribed_courses` **(boolean)** — Has Subscribed Courses 🔒 readonly
- `courses_completion_text` **(char)** — Courses Completion Text 🔒 readonly
- `show_billable_time_target` **(boolean)** — Timesheet Show Rates 🔒 readonly
- `member_of_department` **(boolean)** — Member of department 🔒 readonly
  > Whether the employee is a member of the active user's department or one of it's child department.
- `is_custom_job_title` **(boolean)** — Is Custom Job Title 🔒 readonly
- `is_flexible` **(boolean)** — Is Flexible 🔒 readonly
- `is_fully_flexible` **(boolean)** — Is Fully Flexible 🔒 readonly
- `active_employee` **(boolean)** — Active Employee 🔒 readonly
  > If the active field is set to False, it will allow you to hide the resource record without removing it.
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
