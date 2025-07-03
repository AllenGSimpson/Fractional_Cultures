# goals.md
_A clear charter for the **Victoria 3 — “Patchwork Worlds”** culture‑overhaul mod_

---

## 1 Purpose

* **Replace every vanilla mega‑culture** (e.g., *Han*, *North German*, *Italian*, *Russian*) with the **regional, self‑aware cultures that still existed in 1836**.  
* **Let players watch and influence** the 19th‑century process by which literacy, railways, state policy and war **fuse those patchworks into modern “nation” cultures**.  
* **Enrich diplomacy, revolt risk and migration flavour** without sacrificing AI performance or overwhelming new players.

---

## 2 Design Principles

1. **Historicity First**  
   * Each new tag must be attested as a dialect block, legal estate, or self‑identifying group c. 1800–1870.  
2. **Readable Map, Manageable Lists**  
   * Avoid micro‑tags under ~5 000 POPs at game start; use traits or events for tiny minorities.  
3. **One‑Click Merge Path**  
   * Every bloc ships with an *opt‑in* “Standard Language / Nation‑building” journal chain that can absorb its child cultures when conditions are met.  
4. **Player Agency**  
   * A reformist government can accelerate assimilation; reactionary or federal choices can **freeze the mosaic indefinitely**.  
5. **Performance Safeguards**  
   * Limit each culture‑group to **< 25 tags**; keep homeland geography simple; reuse a single parameterised event template.

---

## 3 Scope (baseline commit)

| Macro‑region | Tags added | Journal chains |
|--------------|-----------|----------------|
| **German lands** | 23 | Hochdeutsch assimilation |
| **Italy** | 17 + 6 diaspora | “Lingua Toscana” unification |
| **Iberia** | 13 (Castilian, Andalusian, Galician…) | Royal Academy 1847 |
| **France** | 18 (Oïl, Oc, Breton, Alsatian…) | Ferry Laws 1882 |
| **Britain & Ireland** | 15 (Scots, Cornish, Ulster‑Scots…) | Education Act 1870 |
| **Nordics** | 22 (Jutlandic, Østnorsk, Scanian…) | School Acts 1842‑1906 |
| **Baltics** | 7 (Latgalian, Samogitian, South Estonian…) | Vernacular Press |
| **Polish lands** | 12 | Odrodzenie Narodowe 1863‑1920 |
| **Rus** | 24 | Russian, Ukrainian, Belarusian revivals |
| **Balkans** | 35 | Standard‑language per supra‑culture |
| **Ottoman Capital** | 2 city cultures (Polis Greek, Polis Turk) | Tanzimat 1840‑76 |
| **China** | 17 Sinitic & Manchu splits | 1905 “Mandarin” reform |
| **Japan** | 8 dialect tags + Ryukyuan & Ainu | Gakusei 1872 |

_Total new culture tags: ≈ 195_

---

## 4 Implementation Milestones

| Milestone | Deliverable |
|-----------|-------------|
| **v0.1 – German & Italian alpha** | All tags in files, homelands, basic POP retag; no events. |
| **v0.2 – Generic “Standard Language” template** | Parameterised journal entry & event that other regions can import. |
| **v0.3 – Europe complete** | Iberia, France, UK, Nordics, Baltics, Poland, Balkans + Constantinople finished. |
| **v0.4 – Eurasia** | East‑Slavic, China, Japan integrated; Taiping & Meiji flavour hooks. |
| **v1.0 – Play‑test release** | All chains functional; AI heuristics tuned; localisation pass. |
| **v1.1+ – Extras** | Dynamic culture spawn (e.g., Plautdietsch, Argentine Welsh), flavour events, achievements. |

---

## 5 Key Game‑Design Goals

* **Diplomatic Complexity** – Great Powers can back specific dialect groups, spawning crises (e.g., “Defend the Polis Greeks”).  
* **Migration Tapestry** – Distinct emigrant flows: Minnan to California, Andalusians to Havana, Ostrobothnians to Michigan.  
* **Revolt Nuance** – Rebel tags inherit only their homeland, preventing unrealistic pan‑regional secessions.  
* **Alt‑History Paths** – A Federal Japan, Hakka‑led Heavenly Kingdom, or Scanian Sweden can survive if the player stifles assimilation.

---

## 6 Non‑Goals (for now)

* **No fantasy cultures or anachronistic ethnicities.**  
* **No province‑level micro‑dialects < 5 k POPs** at start date.  
* **No automatic culture merge without player/AI choice**—nationalisation requires explicit actions.

---

## 7 Contributing Guidelines (TL;DR)

1. **Follow the naming convention** `culture_<region>_<dialect>.txt`.  
2. **Keep homelands tight**—ideally one state, max two.  
3. **Reuse the shared event scripts**; avoid copy‑pasting large blocks.  
4. **Document sources** for each tag in `docs/sources.md`.  
5. **Test assimilation speed**: target full merge in 30–40 in‑game years after decision fires.

---

## 8 Culture breakdown

| Macro-Culture | Sub culture | States |
|--------------|-----------|----------------|
| **German** | Rhenish | FLANDERS 100% ; GELRE 100% ; NORTH_RHINE 70%; RHINELAND 100%; RUHR 40%; WALLONIA 100%; STATE_MOLDAVIA 20%; STATE_DELVIDEK 10%; STATE_EAST_GALICIA 10%; STATE_ROSTOV 20%; STATE_INGRIA 30%; STATE_MOSCOW 40%; STATE_NOVGOROD 30%; STATE_VILNIUS 30%; STATE_KAUNAS 20%; STATE_COURLAND 20%; STATE_RIGA 20%; STATE_TALINN 20%; STATE_MAZOVIA 20%; STATE_GREATER_POLAND 10%; STATE_LESSER_POLAND 20% |
| **German** | Hessian | STATE_HESSE 100%; STATE_MOLDAVIA 20%; STATE_CENTRAL_HUNGARY 20% |
| **German** | Thuringian | STATE_SAXONY 30 % |
| **German** | Saxon | STATE_SAXONY 70 %; STATE_BOHEMIA 40%; STATE_MORAVIA 10%; STATE_NORTHERN_TRANSYLVANIA 70%; STATE_SOUTHERN_TRANSYLVANIA 70%; STATE_EAST_SLOVAKIA 80%; STATE_WEST_SLOVAKIA 60% |
| **German** | Franconian | FRANCONIA 100%; STATE_SLAVONIA 15%; STATE_BANAT 20%; STATE_DELVIDEK 10%; STATE_WEST_GALICIA 15%; STATE_LESSER_POLAND 20%  |
| **German** | Swabian | STATE_TRANSDANUBIA 90%; STATE_SLOVENIA 15%; STATE_WURTTEMBERG 80%; STATE_BADEN 60%; STATE_CROATIA 60%; STATE_SLAVONIA 70%; STATE_MONTENEGRO 40%; STATE_MOLDAVIA 60%; STATE_NORTHERN_TRANSYLVANIA 15%; STATE_SOUTHERN_TRANSYLVANIA 10%; STATE_BANAT 80%; STATE_DELVIDEK 80%; STATE_TRANSDANUBIA 60%; STATE_BEKES 100%; STATE_CENTRAL_HUNGARY 60%; STATE_ROSTOV 20% |
| **German** | Silesian | STATE_SILESIA 100%; STATE_BOHEMIA 30%; STATE_MORAVIA 30%; STATE_EAST_SLOVAKIA 10%; STATE_WEST_SLOVAKIA 20%; STATE_EAST_GALICIA 40%; STATE_WEST_GALICIA 40%; STATE_VILNIUS 20%; STATE_MAZOVIA 10%; STATE_LESSER_POLAND 35% |
| **German** | Alemannic | STATE_ALSACE_LORRAINE 30%; STATE_BADEN 40%; EAST_SWITZERLAND 100%; STATE_WURTTEMBERG 20%; WEST_SWITZERLAND 100%|
| **German** | Bavarian | STATE_BAVARIA 100%; STATE_BOHEMIA 30%; STATE_TYROL 20%; STATE_SLOVENIA 15%; STATE_CROATIA 15%; STATE_SLAVONIA 15%; STATE_TRANSDANUBIA 20%; STATE_EAST_GALICIA 30%; STATE_WEST_GALICIA 25% |
| **German** | Austrian | STATE_AUSTRIA 100%; STATE_STYRIA 100%; STATE_SLOVENIA 70%; STATE_CROATIA 25%; STATE_ISTRIA 100%; STATE_MONTENEGRO 60%; STATE_MORAVIA 60%; STATE_NORTHERN_TRANSYLVANIA 15%; STATE_SOUTHERN_TRANSYLVANIA 20%; STATE_EAST_SLOVAKIA 10%; STATE_WEST_SLOVAKIA 20%; STATE_TRANSDANUBIA 20%; STATE_CENTRAL_HUNGARY 20%; STATE_EAST_GALICIA 10%; STATE_WEST_GALICIA 20% |
| **German** | Tyrolean | STATE_SOUTH_TYROL 100%; STATE_TYROL 70% |
| **German** | Plautdietsch | EAST_PRUSSIA 10%; STATE_ROSTOV 60%; STATE_KAUNAS 10%|
| **German** | Westphalian | WESTPHALIA 100%; NORTH_RHINE 70%; RUHR 60%; STATE_BRUNSWICK 20%; STATE_GREATER_POLAND 15% |
| **German** | Estphalian | STATE_ELBE 80%; STATE_ANHALT 100%; STATE_SCHLESWIG_HOLSTEIN 60%; STATE_HANNOVER 100%; STATE_BRUNSWICK 80%|
| **German** | Pomeranian | WEST_PRUSSIA 30%; POMERANIA 100%; STATE_SCHLESWIG_HOLSTEIN 40%|
| **German** | Prussian | WEST_PRUSSIA 60%; EAST_PRUSSIA 90%; POSEN 70%; STATE_INGRIA 70%; STATE_MOSCOW 60%; STATE_NOVGOROD 70%; STATE_VILNIUS 50%; STATE_KAUNAS 70%; STATE_COURLAND 80%; STATE_RIGA 60%; STATE_TALINN 80%; STATE_TARTU 100%; STATE_MAZOVIA 30%; STATE_GREATER_POLAND 50%; STATE_LESSER_POLAND 25% |
| **German** | Brandenburgish | BRANDENBURG 100%; STATE_POSEN 30% ; ELBE 20%; STATE_RIGA 20%; STATE_MAZOVIA 40%; STATE_GREATER_POLAND 25% |
| **German** | Pennsilfaanisch Deitsch | Pennsylvania |
| **German** | Amish | Ohio and Pennsylvania |
| **German** | Mennonite | Ohio |
| **German-French** | Alsatian | STATE_ALSACE_LORRAINE 50% |
| **Italian** | Lombard | STATE_VENETIA 15%; STATE_TUSCANY 5%; STATE_SAVOY 10%; STATE_EMILIA 5%; STATE_LOMBARDY 80%; STATE_SOUTH_TYROL 40%; STATE_PIEDMONT 15% |
| **Italian** | Piedmontese | STATE_SAVOY 70%; STATE_LOMBARDY 5%; STATE_PIEDMONT 75%; STATE_SARDINIA 10%; STATE_SOUTH_TYROL 10% |
| **Italian** | Emilian | STATE_VENETIA 10%; STATE_ROMAGNA 20%; STATE_TUSCANY 7%; STATE_LOMBARDY 5%; STATE_EMILIA 75%; STATE_PIEDMONT 5%; STATE_UMBRIA 10%; STATE_SOUTH_TYROL 10%|
| **Italian** | Romagnol | STATE_ROMAGNA 60%;  STATE_EMILIA 10%; STATE_LAZIO 5% |
| **Italian** | Venetian | STATE_VENETIA 70%; STATE_SAVOY 10%; STATE_ROMAGNA 10%; STATE_LOMBARDY 10%; STATE_EMILIA 5%; STATE_ISTRIA 100%; STATE_SOUTH_TYROL 30% |
| **Italian** | Tuscan | STATE_TUSCANY 80%; STATE_UMBRIA 30%; STATE_ROMAGNA 10%; STATE_SAVOY 10%; STATE_PIEDMONT 5%; STATE_EMILIA 5%; STATE_UMBRIA 30%; STATE_LAZIO 10%; STATE_ABRUZZO 10%; STATE_SOUTH_TYROL 10%|
| **Italian** | Neapolitan | STATE_CAMPANIA 85%; STATE_ABRUZZO 70%; STATE_CALABRIA 60%; STATE_UMBRIA 10%; STATE_LAZIO 10%; STATE_SICILY 15% |
| **Italian** | Apulian  | STATE_APULIA 100%; STATE_ABRUZZO 10%; STATE_CAMPANIA 5%; STATE_CALABRIA 10%; STATE_SARDINIA 5% |
| **Italian** | Sicilian | STATE_SICILY 85%; STATE_CALABRIA 25%; STATE_CAMPANIA 5% |
| **Italian** | Sardinian | STATE_SARDINIA 85% |
| **Italian-Latin** | Laziale | STATE_LAZIO 70%; STATE_TUSCANY 8%; STATE_UMBRIA 50%; STATE_ABRUZZO 10%; STATE_CAMPANIA 5%; STATE_CALABRIA 5%|
| **Latin** | Roman  | STATE_LAZIO 5% |
| **Iberian** | Old Castillian | Burgos |
| **Iberian** | New Castillian | Madrid |
| **Iberian** | Andalusian | Gibraltar |
| **Iberian** | Astur‑Leonese | León |
| **Iberian** | Galician | Galicia	 |
| **Iberian** | Aragonese | Sobrarbe |
| **Iberian** | Catalan  | Barcelona + Balearic Islands|
| **Iberian** | Valencian | Valencia  |
| **Iberian** | Murcian | Murcia |
| **Basque** | Basque | Navarre  |
| **French** | French | Île‑de‑France |
| **French** | Norman | Normandy
| **French** | Picard | Picardy
| **French** | Champenois‑Lorrain | Lorraine
| **French** | Gallo | not sure
| **French** | Poitou‑Saintongeais | not sure
| **French** | Berrichon‑Orléanais | Orlean |
| **French** | Franco‑Provençal | Savoy |
| **French** | Provençal | not sure |
| **French** | Languedocien | not sure |
| **French** | Gascon | not sure |
| **French** | Auvergnat‑Limousin | not sure |
| **English** | English | Home Countries |
| **English** | Northubrian | Northubria |
| **English** | Mercian | Mercia |
| **English** | West Country | West Country |
| **English** | Kentish | Kent |
| **English** | Anglo-Cornish | Cornwall |
| **English** | Scottish | Scotland |
| **Celtic** | Scots | Scottish Lowlands |
| **Celtic** | Highlander | Scottish Highlands |
| **Celtic** | Cornish | Cornwall |
| **Celtic** | Gaelic | Ireland |
| **English** | Anglo-Irish | Ireland |
| **English** | Ulster-Scots | Ulster |
| **Nordic** | Zealander | Copenhagen |
| **Nordic** | Danish | Copenhagen |
| **Nordic** | Jutlandic | Jutland |
| **Nordic** | Faroese | Faroe Islands |
| **Nordic** | Kalaalisut | Greenland |
| **Nordic** | Sønderjysk | Schleswig Holstein |
| **Nordic** | Icelandic | Iceland |
| **Nordic** | Østnorsk  | Østlandet |
| **Nordic** | Trøndersk | Trøndelag |
| **Nordic** | Nordnorsk | Finnmark coast |
| **Nordic** | Kven | Tornio valleys |
| **Nordic** | Vestnorsk | Stavanger |
| **Nordic** | Svealandic | Stockholm |
| **Nordic** | Götalandic | Västergötland |
| **Nordic** | Skånska | Skåne  |
| **Nordic** | Gutnish | Gotland |
| **Nordic** | Elfdalian | Älvdalen |
| **Nordic** | Norrlandic | Västerbotten |
| **Finnic** | Finnish  | Satakunta |
| **Finnic** | Savonian  | Savo |
| **Finnic** | Karelian | White Sea Karelia |
| **Finnic** | Ålander | Åland isles |
| **Finnic** | Meänkieli  | Torne Valley |
| **Baltic** | Estonian   | North Estonia |
| **Baltic** | Võro  | South Estonia |
| **Baltic** | Seto | Russo-Estonian borderlands |
| **Baltic** | Latvian | West Latvia |
| **Baltic** | Latgalian  | East Latvia |
| **Baltic** | Livonian  | Courland coast |
| **Baltic** | Aukštaitian | High class specific Lithuania |
| **Baltic** | Žemaitian | Low class specific Lithuania |
| **Polish** | Wielkopolski | Posen |
| **Polish** | Kujawsko | Pomeranian Polish |
| **Polish** | Mazowiecki | Warsaw |
| **Polish** | Małopolski | Kraków |
| **Polish** | Góralski | Nowy Targ, Żywiec foothills |
| **Polish** | Ślōnskŏ Godka | Silesian Polish |
| **Polish** | Kaszëbsczi | Gdańsk hinterland, Kartuzy |
| **Polish** | Mazurski | Masuria, southern East Prussia |
| **Polish** | Warmiński | Warmia (Ermland) |
| **Polish** | Podlaski | Podlasie, Bielsk |
| **Polish** | Galicyjski | West Galicia |
| **Polish** | Kresowiak  | Vilnius, Grodno, Volhynia, Lwów city belts |
| **Rus** | Pomor  | White‑Sea coast |
| **Rus** | Vologdan | not_sure |
| **Rus** | Vyatkan | Kirov |
| **Rus** | Kargopolian | not_sure |
| **Rus** | Novgorodian | Ilmen |
| **Rus** | Tverian | not_sure |
| **Rus** | Muscovite | Upper Volga / Moscow |
| **Rus** | Riazanian | not_sure |
| **Rus** | Upper‑Volgan | Kostroma‑Yaroslavl |
| **Rus** | Lower‑Volgan | Nizhny Novgorod, Kazan |
| **Rus** | Donian | Don Host |
| **Rus** | Kubanian  | Kuban Host |
| **Rus** | Azovian | Sea of Azov littoral |
| **Rus** | Black‑Sea Littoral | Kherson‑Mykolaïv |
| **Rus** | Slobodan | Kharkiv‑Sumy |
| **Rus** | Podolian | Vinnytsia |
| **Rus** | Polesian | Pinsk marshes |
| **Rus** | Podlasian | Białystok |
| **Rus** | Grodnian | not_sure |
| **Rus** | Vilnian | Vilna |
| **Rus** | Galician‑Volhynian | not_sure |
| **Rus** | Bessarabian | Chişinău |
| **Rus** | Trans‑Uralian | Tobol‑Irtysh |
| **Rus** | Yeniseian | not_sure |
| **Rus** | Lena‑Olyokmin | not_sure |
| **Rus** | Sakhalin‑Amurian | Russian far east |
| **Rus** | Russian | Standardized |
| **Romanian** | Wallachian | Wallachia south of Carpathians |
| **Romanian** | Moldovan | Moldavia + Russian Bessarabia |
| **Romanian** | Ardelean | Transylvanian Highlands, Apuseni |
| **Romanian** | Crişana | Austrian Banat, Timişoara basin |
| **Romanian** | Bukovinian | Maramureș, Czernowitz fringe |
| **Romanian** | Vlach | Pindus, Epirus, Thessaly, W. Macedonia |
| **Romanian** | Meglenite | Kilkis–Gevgelija pocket |
| **Bulgar** | Moesian_bulgar | Moesia, Ruse, Tarnovo |
| **Bulgar** | Shopluk | Sofia basins, Niš |
| **Bulgar** | Thraco_bulgar | Plovdiv, Burgas, Edirne Villas. |
| **Bulgar** | macedonian_slav | Bitola, Skopje, Ohrid |
| **Bulgar** | Dobrudjan | Coastal Silistra, Constanţa |
| **Bulgar** | Paulician | Vinga & Banat villages |
| **Croat** | Kajkavian | Zagreb, Varaždin, Međimurje |
| **Croat** | Chakavian | Istria, Kvarner, Adriatic isles |
| **Croat** | Slavonian | Slavonia, Vukovar, Brod |
| **Croat** | Shtokavian | Dalmatian coast, Split, Dubrovnik |
| **Serb** | Bačka | Novi Sad, Pančevo |
| **Serb** | Šumadija | Kragujevac, Niška krajina |
| **Serb** | Herzegovinian | Trebinje, Bileća |
| **Serb** | Montenegrin | Cetinje, Nikšić |
| **Bosniak** | Bosniak | Sarajevo, Zenica |
| **Bosniak** | Sanjak | Sandžak corridor |
| **Slovene** | Carniolan | Ljubljana basin |
| **Slovene** | Primorska | Athens, Aegean coast, Phanar |
| **Hellenic** | Phanariot | Vinga & Banat villages |
| **Hellenic** | Moraiot | Peloponnese |
| **Hellenic** | Cycladic | Aegean island states |
| **Hellenic** | Heptanese | Ionian Islands |
| **Hellenic** | Cretan | Crete |
| **Hellenic** | Pontic | Trebizond & Anatolian Pontus |
| **Hellenic** | Cyprean | Cyprus |
| **Hellenic** | Cappadocian | Kayseri–Göreme villages |
| **Hellenic** | Constantinopolitan  | Constantinople |
| **Albanic** | gheg | Shkodër, Kosovo, Krujë |
| **Albanic** | tosk | Vlorë, Korçë, Berat |
| **Albanic** | arvanite | Attica‑Boeotia villages, Euboea |
| **Turkic** | Rumelian | Salonica, Eastern Thrace, Dobruja towns, Bosnia garrisons |
| **Turkic** | Stambuli | Istanbul |
| **Turkic** | aegean_turk | İzmir–Aydın |
| **Turkic** | central_anatolian | Ankara–Konya |
| **Turkic** | eastern_anatolian | Erzurum–Kars |
| **Turkic** | karadeniz_turk | Trabzon–Samsun |
| **Turkic** | karamanli | Christian‑Turk minority |
| **Turkic** | caucasian_turk | Terek & Erzurum Turkmens |
| **Chinese** | zhongyuan | Henan, south Hebei, north Anhui |
| **Chinese** | dongbei_han | Fengtian, Jilin, Heilongjiang |
| **Chinese** | Jilu‑Shandong | Shandong peninsula, Tianjin coast |
| **Chinese** | Jin‑Shaan | Shanxi, Shaanxi, Gansu corridor |
| **Chinese** | Ba‑Shu | Sichuan, Chongqing, eastern Xikang |
| **Chinese** | jianghuai | Jiangsu north of Yangtze, central Anhui, Hubei river belt |
| **Chinese** | Wu | Jiangsu south of Yangtze, Zhejiang, Shanghai, Ningbo |
| **Chinese** | Gan | Jiangxi |
| **Chinese** | Xiang | Hunan |
| **Chinese** | Miao | not sure |
| **Chinese** | Zhuang | not sure |
| **Chinese** | Yao | not sure |
| **Chinese** | Dong | not sure |
| **Chinese** | Tujia | not sure |
| **Chinese** | Hui | Shaanxi–Gansu–Ningxia & Yunnan muslims |
| **Chinese** | Minnan | 	Zhangzhou, Quanzhou, Xiamen + Teochew (Chaoshan) |
| **Chinese** | Mindong | Fuzhou, Ningde |
| **Chinese** | Yue/Cantonese | Guangdong west+Pearl delta, Hong Kong, Guangxi east |
| **Chinese** | Hakka | 	Meizhou, Tingzhou, North‑east Guangdong, South Jiangxi |
| **Japanese** | edo | Edo (Tokyo), Musashi, Sagami, Shimosa, Kōzuke |
| **Japanese** | tohoku | Sendai, Morioka, Aizu |
| **Japanese** | hokuriku | Kanazawa, Fukui, Toyama (Kaga & Echizen) |
| **Japanese** | kansai | Kyoto, Osaka, Nara, Ōmi |
| **Japanese** | chugoku | Hiroshima (Chōshū), Okayama, Shimane |
| **Japanese** | shikoku | Tokushima (Awa), Kōchi (Tosa), Ehime (Iyo) |
| **Japanese** | kyushu | Satsuma, Hizen, Kumamoto, Nagasaki |
| **Japanese** | ezo | Hakodate & Ishikari (early settler villages) |
| **Japanese** | ryukyuan | Ryukyu Kingdom (Okinawa & Amami) |
| **Kurdish** | kurmanji | Van, Diyarbakır, Bitlis |
| **Kurdish** | zaza | Dersim, Bingöl |
| **Kurdish** | sorani | Mosul vilayet |
| **Kurdish** | Assyrian | Vanilla (keep) |
| **Arabic** | iraqi_arab  | Baghdad, Basra |
| **Arabic** | levantine_arab  | Damascus, Beirut, Aleppo |
| **Arabic** | mashriqi | Hejaz |
