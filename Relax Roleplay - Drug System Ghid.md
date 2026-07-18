# 💊 Wiki Relax-Roleplay: Sistemul Avansat de Droguri

Acesta este documentul tehnic complet al sistemului `rlrp_drugs`. Aici sunt detaliate toate mecanicile ascunse, statisticile, rețetele și efectele drogurilor de pe server.

---

## 🔬 1. Sistemul de Calitate și "Țepele"

Orice drog de pe server are **4 calități distincte**. Calitatea determină cât de puternic este efectul pozitiv, dar și cât de mult crește gradul de dependență (adicția).

1. **Low (Slab)**: Efecte minime, crește adicția cel mai mult.
2. **Med (Mediu)**: Efecte echilibrate, adicție moderată.
3. **High (Premium)**: Efecte maxime, șanse minime de adicție.
4. **Fake (Fals)**: Item de țeapă (scam). Arată la fel ca drogul Premium în inventar, dar oferă doar debuff-uri majore (îți scade HP-ul sau îți ia din viteză) și dă o dependență garantată (100%).

> [!TIP]
> **Roleplay:** Itemele *Fake* pot fi vândute de jucători pe stradă. Jucătorul neatent care nu citește descrierea ("Iarba care miroase a pizza") va folosi drogul și va lua debuff-uri în loc de buff-uri.

---

## 🛠️ 2. Mesele de Preparare (Crafting)

Prelucrarea drogurilor durează **10 secunde** și este strict limitată pentru a preveni "farmatul" abuziv.

*   **Limita Standard:** Un jucător poate folosi masa de doar **2 ori** la un interval de 30 de zile.
*   **Limita VIP:** Dacă este activată din configurare (`EnableVipLimits`), VIP-urile au acces la mai multe preparări.

### Tipuri de Mese:
| Nume | Permisiuni Calitate | Prop / Obiect folosit |
| :--- | :--- | :--- |
| **Masa Standard** | Calitate *Slabă (Low)* și *Fake* | `bkr_prop_weed_table_01a` (Masa de lemn) |
| **Masa Medie/Industrială**| Calitate *Medie (Med)* și *Premium (High)*| `bkr_prop_meth_table01a` (Masa industrială) |

---

## 🌿 3. Profilul Drogurilor

Aici sunt exact efectele și ingredientele de care ai nevoie pentru a crea fiecare drog la masă. Toate drogurile necesită materia primă + 1x pungă zippo (`zipbag`).

### 🥦 Marijuana (Cui)
Marijuana este axată pe relaxare și refacerea lentă a sănătății.
*   **Timp Consum:** 5 secunde
*   **Comenzi Animații:** `/e joint` sau `/e smokeweed`
*   **Durată Efecte:** 5 minute

| Calitate | Ingredient Brut | Item Rezultat | Regenerare HP | Scădere Stres | Creștere HP Max | Adicție |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Slabă** | `weed_bud_low` | `weed_low` | +1 HP / tick | -15 Stres | - | 20% |
| **Medie** | `weed_bud_med` | `weed_med` | +2 HP / tick | -30 Stres | - | 10% |
| **Premium** | `weed_bud_high` | `weed_high` | +3 HP / tick | -50 Stres | +5% Permanent | 5% |
| **Fake** | `oregano` | `weed_fake` | **-5 HP / tick** | **+100 Stres** | - | 100% |

---

### ❄️ Cocaină
Cocaina este drogul agresivității și al vitezei. Perfect pentru fugi de poliție sau lupte corp la corp.
*   **Timp Consum:** 4 secunde
*   **Comenzi Animații:** `/e sniff` sau `/e coke`
*   **Durată Efecte:** 3 minute

| Calitate | Ingredient Brut | Item Rezultat | Boost Viteză | Damage Pumni | Tremurat Țintă | Adicție |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Slabă** | `coke_leaf_low` | `coke_low` | +10% | +25% | Mic (0.3) | 30% |
| **Medie** | `coke_leaf_med` | `coke_med` | +22% | +60% | Mediu (0.8) | 20% |
| **Premium** | `coke_leaf_high` | `coke_high` | +35% | **+100% (Dublu)** | Mare (1.4) | 10% |
| **Fake** | `baking_soda` | `coke_fake` | **-50%** | **-90%** | Imposibil (3.0)| 100% |

---

### 💎 Metamfetamină (Meth)
Meth este drogul de luptă "Tank". Îți scade masiv damage-ul primit de la gloanțe și te face imun la căzături.
*   **Timp Consum:** 6 secunde
*   **Comenzi Animații:** `/e smokepipe` sau `/e meth`
*   **Durată Efecte:** 4 minute

| Calitate | Ingredient Brut | Item Rezultat | Damage Primit | Imunitate Ragdoll | Efect Vizual | Adicție |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Slabă** | `meth_chemical_low`| `meth_low` | 85% (-15%) | Da | Da | 40% |
| **Medie** | `meth_chemical_med`| `meth_med` | 70% (-30%) | Da | Da | 30% |
| **Premium** | `meth_chemical_high`|`meth_high` | **50% (Jumătate)** | Da | Da | 15% |
| **Fake** | `detergent` | `meth_fake` | **200% (Dublu)** | **Nu** | Da | 100% |

---

## 🤢 4. Adicția, Sevrajul și Reabilitarea

Fiecare consum de droguri adaugă un anumit procentaj la **Nivelul de Adicție** (până la 100%).

### Efectele Adicției (Halucinații)
Când consumi prea mult și atingi anumite praguri, caracterul va suferi efecte de ecran:
*   **La 25%:** Ecran ușor blurat (`spectator5`)
*   **La 50%:** Amețeală și beție vizuală (`Drunk`)
*   **La 75%:** Distorsiune a culorilor (`biker_weed_nodebris`)
*   **La 100% (Supradoză):** Culori sparte și ecran mișcat grav (`stoned`)

### Sevrajul (Withdrawal)
Dacă adicția ta este peste **30%** și nu ai consumat droguri recent, o dată la 2 minute ai **65% șansă** să intri în Sevraj timp de 15 secunde.
> [!WARNING]
> **Ce se întâmplă în Sevraj?**
> * Camera tremură puternic (Shake 0.6)
> * Pierzi HP continuu (3 HP / secundă)
> * Personajul tău aleargă cu 15% mai încet (Speed Debuff 0.85)

### Clinica de Reabilitare
Dacă vrei să scapi de dependență, trebuie să faci rost de itemul `rehab_pills` (Pastile de Reabilitare).
*   **O pastilă scade adicția cu 35%**.
*   Consumul durează 6 secunde ("Iei tratamentul de reabilitare...").
*   Te sfătuim să adaugi acest item la un NPC Doctor de la spital pentru a încuraja roleplay-ul medical.
