# Tabel Atribuire Permisiuni & Comenzi (Versiunea Finală Actualizată)

Mai jos găsești lista completă și la zi cu **toate** scripturile modificate, inclusiv cele pe care le-am rezolvat adineauri (banking, eup, multicharacter, inventory, vehiclefailure). Am eliminat definitiv toate vechile "array-uri" care conțineau grade multiple.

### 1. Nucleul Serverului (QBCore Core)

| Script | Comandă / Funcție | Rol Vechi / Problemă | Rol Nou |
| :--- | :--- | :--- | :--- |
| `qb-core` | Toate comenzile de bază (ex: `/car`, `/setjob`, `/dv`) | `admin` | **Mapate Ierarhic** (ex: `admin level 2`) |
| `qb-core` | Comenzile de management (ex: `/openserver`) | `god` / `admin` | **Management Team** |
| `qb-core` | `/addpermission`, `/removepermission` | `god` | **Founder** |
| `qb-core` | Evenimente Backend & Bypass Licențe | `admin` | **Senior Admin** |
| `qb-core/config.lua`| Array-ul central `QBConfig.Server.Permissions` | Vechea listă (operator, trusted etc.) | **Actualizat complet** la ierarhia ta nouă de Discord. |

### 2. Afaceri, Magazine, Bănci & Benzinării

| Script | Comandă / Funcție | Rol Vechi | Rol Nou |
| :--- | :--- | :--- | :--- |
| `rlrp_businesses` | `/createbusiness`, `/editbusinesses` | `admin` | **Founder** |
| `rlrp_businesses` | `/pmreset` (Resetare ore PM) | `admin` | **Community Manager** |
| `rlrp_businesses` | `/pmstats` (Vezi statistici afaceri) | `admin` | **User** |
| `rlrp_businesses` | Securitate Backend (Ștergere, Creare) | `admin` | **Founder** |
| `rlrp_shops` | `/addruns` (Adaugă curse marfă) | `admin` | **Senior Admin** |
| `rlrp_shops` | `/refresh_shops` (Sincronizare forțată) | `admin` | **Management Team** |
| `rlrp_shops` | Funcție internă `IsAdmin()` (Bypass stoc) | `admin` / `founder` | **Management Team** |
| `rlrp_fuel` | `/adminfillwarehouse` (Stoc infinit temporar) | `admin` | **Founder** |
| `rlrp_fuel` | Funcție internă `IsAdmin()` | `admin` | **Founder** |
| `lb-businessapp` | Acces total în aplicația de pe telefon | `admin` | **Management Team** |
| `rlrp_banking` | `/setbankvip` | `admin` | **Management Team** |

### 3. Utilitare Administrare & Faction/EUP

| Script | Comandă / Funcție | Rol Vechi | Rol Nou |
| :--- | :--- | :--- | :--- |
| `rlrp_drugs` | `/spawntable`, `/edittables`, `/adminmese` | `admin` | **Founder** |
| `rlrp_drugs` | `/testdrugs` | `admin` | **Founder** |
| `rlrp_drugs` | `/resetaddiction`, `/resetcraft` | `admin` | **Senior Admin** |
| `rlrp_drugs` | Securitate Backend (Salvare mese) | `admin` | **Founder** |
| `rlrp_gym` | `/setstat` (Modifică forțat mușchii/stamina) | `admin` | **Senior Admin** |
| `rlrp_nametag` | `/addRP`, `/removeRP` | `admin` | **Admin Level 1** |
| `rlrp_nametag` | `/cidtag` (Afișare ID-uri deasupra capului)| `admin` | **Trial Admin** |
| `rlrp_referral` | `/addinvites`, `/removeinvites` | `admin` | **Management Team** |
| `rlrp_chat` | `/ann`, `/event` (Anunțuri globale) | `god` | **Trial Admin** |
| `rlrp_bikemanager` | `/createbike` (Spawn bicicletă de decor) | `admin` | **Founder** |
| `rlrp_eup` | `/aeup` (Meniul Ascuns EUP de admin) | `admin` | **Admin Level 1** |

### 4. Standalone, Inventar, Vehicule & Alte Scripturi

| Script | Comandă / Funcție | Rol Vechi / Problemă | Rol Nou |
| :--- | :--- | :--- | :--- |
| `qb-inventory` | `/gg` (Give Item) & `/clearinv` (Șterge Inv.) | Lista multiplă (operator, trusted etc.) | **Founder** (singur, fără array-uri) |
| `qb-vehiclefailure` | `/fix` (Repară Mașina Instant) | Lista multiplă | **Admin Level 1** |
| `qb-vehiclefailure` | `/dl` (Afișează info/Damage Vehicul) | Lista multiplă | **Trial Admin** |
| `ZSX_Multicharacter`| Permisiuni administrative multichar | `admin` | **Founder** |
| `qb-weathersync` | Toate: `/weather`, `/time`, `/freezetime`, etc. | `admin` | **Senior Admin** |
| `codem-wallet` | Acces Admin Portofel (Config `AdminPermissions`) | `admin`, `superadmin` | **Management Team** / **Founder** |
| `kq_shellbuilder` | Construcție MLO/Shell custom | `admin` | **Founder** |
| `txAdmin` / `FiveM` | `group.admin` ACE (Protecție nativă) | `-` | Prin server.cfg atribuit direct la **qbcore.founder** |

---
*Reamintire tehnică: Sistemul este acum curat (o singură comandă = un singur grad cerut). Orice grad superior celui cerut (de exemplu Founder) are acces automat la absolut tot ce e sub el!*
