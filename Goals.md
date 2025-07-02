# Goals.md  
*Victoria 3 “American Nations” Culture‑Flavour Mod*  

---

## 1 . Why we are doing this  
* **Pain point** –  Vanilla Victoria 3 collapses the entire United States into two Anglo cultures (Yankee & Dixie).  
* **Goal** –  Re‑create the regional tapestry described in Colin Woodard’s *American Nations* while staying within normal V3 mechanics (no DLL hacks, only `.txt` & `.lua`).  
* **Success looks like** –  A 1836 USA that already *plays* differently in Boston, Charleston, and New Orleans; a frontier that spawns its own identities; Civil‑War and immigration events that read the new tags; and clear economic flavour through obsessions & taboos.

---

## 2 . Scope & deliverables  

| Area | Must‑have | Nice‑to‑have |
|------|-----------|--------------|
| **Culture definitions** | 9 static + 4 dynamic cultures, complete with homelands | Plausible POP name lists per culture |
| **Obsessions & taboos** | Table below implemented in `00_cultures.txt` | Event chains that *change* them via reforms |
| **Religion re‑enable** | Fully playable **Mormon** faith: taboos, IG ideology, start pops, migration events | Unique “Plural‑Marriage” law branch |
| **Event / JE scripting** | Regional Identities, Frontier Foundation chain, Civil‑War & Immigration edits | Dynamic tension events (e.g., Temperance riots) |
| **Balance pass** | IG attraction modifiers, price‑spread sanity check | AI personality tweaks per culture |
| **Documentation** | This Goals.md + change log | Steam‑workshop page copy |

---

## 3 . Cultures to add  

### 3.1  *Static, present on 1 Jan 1836*

| Tag | Display name | Core homelands | One‑liner flavour |
|-----|--------------|----------------|------------------|
| `new_englander` | New Englander | New England + upstate NY | Literacy, temperance, abolitionist leanings |
| `midlander` | Midlander | PA, NJ, DE, north‑MD | Quaker/German pluralism, industry & farming |
| `chesapeake` | Chesapeake | Tidewater VA + coastal NC | Old planter gentry, Anglophile |
| `deep_south` | Deep South | SC, GA, AL lowlands, MS delta, FL panhandle | Cotton barony, rigid hierarchy |
| `appalachian` | Appalachian | WV, KY, TN hills, Ozarks | Scots‑Irish populism, frontier ethos |
| `new_nether` | Knickerbocker | NYC & lower Hudson | Cosmopolitan commerce, finance |
| `louisiana_creole` | Louisiana Creole | Lower Mississippi & Acadiana | Francophone, Catholic, mercantile |
| `tejano` | Tejano | South Texas (Nueces Strip) | Hispano ranch culture |
| `nuevo_mexicano` | Nuevomexicano | New Mexico & S. Colorado | Pueblo‑intermarried Hispanos |

### 3.2  *Dynamic frontier cultures* (appear via Journal Entries)

| Tag | Display name | Trigger window & states |
|-----|--------------|-------------------------|
| `prairie` | Prairie Settler | 1850‑75, IA/IL/MN/KS/NE/DAK when >250 k mixed Anglo pops |
| `mountain_west` | Mountain West | 1860‑95, Rockies >100 k Anglo pops |
| `pacific_american` | Pacific American | 1860‑1900, CA + OR + WA >300 k Anglos |
| `texan` | Texan | When Republic annexed *or* TX state pops >300 k Anglos |

*All cultures stay inside the vanilla **Anglo** culture‑group so migration & assimilation mechanics remain unchanged.*

---

## 4 . Obsessions & taboos  

| Culture | **Obsessions** (max 2) | **Taboos** (max 2) | Notes |
|---------|------------------------|--------------------|-------|
| New Englander | Paper | Liquor | Temperance + print industry |
| Midlander | Furniture | Small Arms | Quaker pacifism; cabinetry craft |
| Chesapeake | Wine, Luxury Clothes | — | Anglophile planter tastes |
| Deep South | Tobacco, Sugar | — | Cash‑crop self‑consumption |
| Appalachian | Small Arms, Liquor | Wine | Guns & moonshine; disdain for fancy wines |
| Knickerbocker | Services | — | Port finance & entertainment |
| Louisiana Creole | Wine, Sugar | — | French cuisine & cane‑sweet tooth |
| Tejano | Meat | — | Beef ranching |
| Nuevomexicano | Clothes (wool) | Liquor | Churro‑wool weaving; Catholic blue laws |
| Prairie Settler | Small Arms, Tools | — | Machinery love, spartan homes |
| Mountain West | Sugar | Liquor, Coffee | Mormon beets; Word‑of‑Wisdom bans |
| Pacific American | Tea, Fish | — | Pacific trade & salmon diet |
| Texan | Small Arms, Meat | — | “Come and Take It” + brisket |

---

## 5 . Religion addition – **Mormon (Latter‑day Saint)**  

| Key | Value |
|-----|-------|
| **Religion tag** | `mormon` (display: *Latter‑day Saint*) |
| **Religion group** | `christian` (same level as Protestant/Catholic) |
| **Taboos** | `liquor`, `coffee`, `tobacco` (Word‑of‑Wisdom) |
| **Obsessions** | `sugar` (beet‑sugar industry in Utah) |
| **Default clergy IG ideology** | `theocratic_republican`<sup>†</sup> – supports *Theocracy* & *Republicanism*, opposes *State Atheism* |
| **Start pops (1836)** | ~15 k spread across *Western NY (Palmyra)*, *Kirtland OH*, *Jackson MO* |
| **Guaranteed homeland** | Added automatically to **Mountain West** states once that culture spawns |
| **Conversion rules** | Normal missionary spread; bonus +25 % chance for Protestant pops in Mountain states during 1840‑1890 |

<sup>† If Paradox never shipped LDS‑specific ideology, clone Protestant ideology and tweak stance weights.*

### Why a separate religion, not a Protestant sect?  
By 1844 the LDS church had its own canon, migration polity, and theocratic aspirations. Distinct treatment lets us model **religious discrimination** and the subsequent Utah‑centric state‑building.  :contentReference[oaicite:0]{index=0}  

--- 

## 6 . Mechanical hooks  

* **Cultures ↔ Religion** – `mountain_west` spawns with `mormon` as *default faith*. Other cultures keep vanilla defaults.  
* **IG attraction** – Pops of the Mormon faith gain *+20 Devout IG approval* when Utah is their primary homeland; −10 elsewhere (mirrors Deseret‑centric loyalty).  
* **Acceptance matrix** – USA initially *tolerates* Mormon pops; `theocracy` or `state_religion` laws can flip that to accepted or discriminated.  
* **Price‑spread logic** – Mormon taboos overlap perfectly with Mountain West cultural taboos, reinforcing high regional sugar prices and discouraging liquor industry there.

---

## 7 . Event & Journal Entry outline  

| Name | Who gets it | What it does |
|------|-------------|--------------|
| **“The Restoration”** (1830) | USA | Creates first tiny Mormon pops in Palmyra NY; unlocks later chain. |
| **“Zion’s Camp”** (1833‑38) | USA | If country has Religious Schools OR pops are discriminated, small LDS pops migrate to *Missouri* then *Illinois*; turmoil if MO/IL discriminate. |
| **“The Exodus to Deseret”** (fires 1846 if LDS pops >30 k & still discriminated) | USA | Spawns migration wave to unorganised Utah, adds *Mormon* homeland to Utah, unlocks Deseret tag if Utah becomes incorporated. |
| **“Utah War”** (optional, 1857‑59) | USA | If Utah has >70 % Mormon pops and USA has *State Religion* (Protestant), can trigger conflict or compromise granting autonomy. |
| **Frontier Foundation – Mountain West** | *as before* | On Stage 3 the JE also **automatically promotes** `protestant` pops in Utah to `mormon` and adds LDS‑specific modifiers. |

---


## 8 . Map cheatsheet (religious start, 1836)

```text
Palmyra NY     – 9k Mormon
Kirtland OH    – 4k Mormon
Independence MO– 2k Mormon
Elsewhere USA  – Protestant / Catholic per vanilla
```

## 9 . Map cheatsheet (static homelands, 1836)

```text
New Englander  – ME, NH, VT, MA, RI, CT, Upper NY, NE OH
Knickerbocker  – NYC five boroughs, Long Island, lower Hudson
Midlander      – PA, NJ, DE, MD (north shore)
Chesapeake     – VA Tidewater, coastal NC
Deep South     – SC, GA, AL (coast & black belt), MS delta, FL panhandle
Appalachian    – WV, KY, TN highlands, western VA/NC foothills, Ozarks
Louisiana Creole– Orleans & Acadiana parishes
Tejano         – South TX (future Nueces Strip)
Nuevomexicano  – NM & S. Colorado
```