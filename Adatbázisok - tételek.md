# Adatbázisok - tételek

## Tartalomjegyzék

1. [Adatbázisok alapjai](#Adatbázisok-alapjai)
   1. [Adat, információ, tudás. Metaadatok. Strukturált, szemistrukturált és nem strukturált adatok.](#adat-információ-tudás-metaadatok-strukturált-szemistrukturált-és-nem-strukturált-adatok)
   2. [Adatbázis-kezelő fogalma, feladatai, felépítése, használói](#adatbázis-kezelő-fogalma-feladatai-felépítése-használói)
2. [A fizikai adatbázis](#a-fizikai-adatbázis)
   1. [Heap szervezés](#heap-szervezés)
   2. [Hash-állományok](#hash-állományok)
   3. [Indexelt állományok](#indexelt-állományok)
   4. [Ritka indexek](#ritka-indexek)
   5. [B*-fák](#b-fák)
   6. [Sűrű indexek, előnyök és hátrányok](#sűrű-indexek-előnyök-és-hátrányok)
   7. [Változó hosszúságú rekordok kezelése](#változó-hosszúságú-rekordok-kezelése)
   8. [Részleges információ alapján történő keresés](#részleges-információ-alapján-történő-keresés)
   9. [Több kulcs szerinti keresés támogatása](#több-kulcs-szerinti-keresés-támogatása)
3. [A logikai adatbázis](#a-logikai-adatbázis)
   1. [Adatmodellek, modellezés](#adatmodellek-modellezés)
   2. [Az E-R modell és elemei](#az-e-r-modell-és-elemei)
   4. [A relációs adatmodell: adatok strukturálása és műveletek](#a-relációs-adatmodell-adatok-strukturálása-és-műveletek)
   5. [Relációalgebra](#relációalgebra)
   6. [Sorkalkulus, oszlopkalkulus](#sorkalkulus-oszlopkalkulus)
   7. [Biztonságosság](#biztonságosság)
4. [Lekérdezés-optimalizálás](#lekérdezés-optimalizálás)
   1. [Relációs lekérdezések heurisztikus optimalizálása](#relációs-lekérdezések-heurisztikus-optimalizálása)
   2. [Relációalgebrai kifejezések transzformációi, ekvivalens kifejezések](#relációalgebrai-kifejezések-transzformációi,-ekvivalens-kifejezések)
   3. [Relációs lekérdezések költségbecslés alapú optimalizálása](#relációs-lekérdezések-költségbecslés-alapú-optimalizálása)
   4. [Katalógusban tárolt információk](#katalógusban-tárolt-információk)
   5. [A lekérdezés költsége: szelekció, indexelt szelekció, join műveletek és algoritmusok, egyéb műveletek](#a-lekérdezés-költsége-szelekció-indexelt-szelekció-join-műveletek-és-algoritmusok-egyéb-műveletek)
   6. [Materializáció és pipelining](#materializáció-és-pipelining)
   7. [A kiértékelési terv kiválasztása](#a-kiértékelési-terv-kiválasztása)
5. [Adatbázisok logikai tervezése](#adatbázisok-logikai-tervezése)
   1. [Relációs adatbázis sémák tervezése E-R diagramból](#relációs-adatbázis-sémák-tervezése-e-r-diagramból)
   2. [Anomáliák (módosítási, törlési, beszúrási)](#anomáliák-(módosítási-törlési-beszúrási))
   3. [Adatbázis kényszerek, redundancia](#adatbázis-kényszerek-redundancia)
   4. [Funkcionális függőségek](#funkcionális-függőségek)
   5. [Relációs sémák kulcsai](#relációs-sémák-kulcsai)
   6. [Armstrong axiómái a funkcionális függőségekről](#armstrong-axiómái-a-funkcionális-függőségekről)
   7. [Az első normálforma (1NF)](#az-első-normálforma-(1NF))
   8. [A második normálforma (2NF)](#a-második-normálforma-(2NF))
   9. [A harmadik normálforma (3NF)](#a-harmadik-normálforma-(3NF))
   10. [A Boyce-Codd normálforma (BCNF)](#a-Boyce-Codd-normálforma-(BCNF))
6. [Tranzakció-kezelés](#tranzakció-kezelés)
   1. [ACID tulajdonságok adatbázis-kezelő rendszerekben](#acid-tulajdonságok-adatbázis-kezelő-rendszerekben)
   2. [Ütemezések fajtái](#ütemezések-fajtái)
   3. [Lost update, non-repetable read, phantom read, dirty data](#lost-update-non-repetable-read-phantom-read-dirty-data)
   4. [Problémák a zárakkal: pattok és éhezés](#problémák-a-zárakkal-pattok-és-éhezés)
   5. [Tranzakció modellek](#tranzakció-modellek)
   6. [Kétfázisú zárolás (2PL)](#kétfázisú-zárolás-(2PL))
   7. [A fa protokoll](#a-fa-protokoll)
   8. [A figyelmeztető protokoll](#a-figyelmeztető-protokoll)
   9. [Tranzakcióhibák kezelése, commit pont](#tranzakcióhibák-kezelése-commit-pont)
   10. [Szigorú kétfázisú protokoll (szigorú 2PL)](#szigorú-kétfázisú-protokoll-(szigorú-2PL))
   11. [Agresszív és konzervatív protokollok](#agresszív-és-konzervatív-protokollok)
   12. [Védekezés rendszerhibák ellen](#védekezés-rendszerhibák-ellen)
   13. [Hatékonysági kérdések](#hatékonysági-kérdések)
   14. [A redo protokoll: naplózás és helyreállítás](#a-redo-protokoll-naplózás-és-helyreállítás)
   15. [Ellenőrzési pontok (checkpointing)](#ellenőrzési-pontok-(checkpointing))
   16. [Időbélyeges tranzakciókezelés R/W modellben](#időbélyeges-tranzakciókezelés-R/W-modellben)
   17. [Az időbélyeges R/W modell és a 2PL összehasonlítása](#az-időbélyeges-R/W-modell-és-a-2PL-összehasonlítása)
   18. [Tranzakcióhibák és az időbélyegek](#tranzakcióhibák-és-az-időbélyegek)
   19. [Verziókezelés időbélyegek mellett (MVCC)](#verziókezelés-időbélyegek-mellett-(MVCC))

## Adatbázisok alapjai

### Adat, információ, tudás. Metaadatok. Strukturált, szemistrukturált és nem strukturált adatok.

Adat, információ, tudás: 🧓🏼 G4jd0s stuff

#### Metaadatok

A tárolt adatok sémáját leíró adatok (pl egy embert a neve, életkora és magassága jellemzi, ahol a neve egy max 128 karakteres UTF8 string, az életkora egy 4 byte-os `int`, a magassága pedig egy `real` ).

#### Adatok strukturáltsága

Azt jelenti, hogy az adatbázisban tárolt adatok mennyire vann szétbontva, és az adatbázissal mennyire részletesen lehet lekérdezni/hozzáférni.

Nem strukturált adatokra példa, ha az összes adatot szövegként egy hatalmas XML file-ban lenne tárolva, így viszont az adatbázis max. szöveg-manipulációs függvényekkel férhet hozzá.

Szemi-strukturált adatokra példa, ha pl. egy blogon a posztok JSON-ban string-ként vannak tárolva, de a pl. publikálás dátuma, szerzője és a poszt címe már külön mező a posztokat tároló tábla sémájában. 

Teljesen strukturált adatoknál minden "atomi" adat (tehát amik külön már nem lennének értelmesek, pl számok, stringek, dátumok, koordináták) külön mező.

### Adatbázis-kezelő fogalma, feladatai, felépítése, használói

#### Adatbázis-kezelő fogalma

Az a "program" (és a hozzá tartozó infrastruktúra), ami a logikai adatbázist implementálja. Része a DDL és DML nyelvek implementációja, az adatbázis-menedzser, és az állománykezelő.

#### Az adatbázis-kezelő feladatai

- Az adatbázis-séma értelmezése és tárolása (DDL)
- A felhasználói lekérdezések végrehajtása (DML)
- A fizikai tárolás megvalósítása
- Adatvédelem: a felhasználók privilégiumok szerinti elkülönítése
- Adatbiztonság: az adatok extrém csapások után is maradjanak elérhetőek
- Integritás: az adatbázisban tárolt adatok mindig legyenek "helyesek". A helyesség arra utal, hogy 1) egy adott mezőhöz tartozó kényszerek be legyenek tartva 2) referenciális integritás megmaradjon (pl idegen kulcsok esetén)
- Szinkronitás: több felhasználós működés esetén ne legyen "áthallás" a felhasználók között

#### Tipikus felhasználók

Lásd jegyzet 1.3

#### Az adatbázis-kezelő (logikai) felépítése

![Az adatbázis-kezelő (logikai) felépítése](assets/dbms-structure.png)

![Az adatbázis-kezelő rétegmodellje](assets/dbms-layers.png)

(forrás: jegyzet)

A rétegmodellben a rétegek lehetővé teszik, hogy a mindegyik réteg csak a saját szomszédainak interface-étől függjön, azaz pl a keresési implementációja akármilyen fizikai hardverrel együtt tud működni (pl in-memory vagy disk alapú).

## A fizikai adatbázis

Egy adatbázis fizikai része lehet diszkrezidens vagy memóriarezidens. A fizikai szervezés implementálásában

- keresés
- beszúrás
- törlés
- módosítás

műveletek hatékonysága az elsődleges szempont.

A fizikai tárolásban használt "elemek" hierarchiája valami ilyesmi:

- a teljes adatbázis tárolására használt háttértár
  - file-ok: az oprendszer kezeli őket
    - blokkok
      - rekordok

A blokkok mérete kilobájtokban mérhető méretű, csak egy relatíve alacsony, fix mennyiségű tárolható egyszerre az operatív tárban (RAM-ban). A fenti 4 művelet hatékonyságát az határozza meg, hogy egy blokk tartalmát hányszor kell a háttértárból kiolvasni. A blokkok rendelkeznek egy fejléccel, ahol a tartalmazott rekordokra vonatkozó metaadatok tárolódnak (pl melyik rekord van törölve).

A rekordok [header, record*] struktúrával rendelkeznek. Egy rekord szabad, ha az adatbázisban nincs rá mutató pointer (ellenkező esetben kötött). A rekordok tartalmazhatnak ismétlődő hosszúságú mezőket.

Jelölések:

```
b: blokkméret (fejléc nélkül)
s_r: az r állomány rekordmérete
n_r: az r állomány rekordjainak száma
f_r: az r állományban egy blokkban elhelyezkedő rekordok száma (blocking factor): floor(b / s_r)
b_r: az r állomány által elfoglalt blokkok száma: ceil(n_r / f_r)
```

### Heap szervezés

Ebben az esetben ay adatok mindenféle segédstruktúra nélkül, "kupacban" vannak tárolva. A 4 művelet a következőképpen alakul:

- Keresés: lineáris kereséssel minden blokkot végig kell nézni a keresett rekordokért. Mivel a legjobb esetben egyből meglesz a keresett rekord, legrosszabb esetben pedig az utolsóként sorra kerülő blokkban van, átlagosan `blokkok száma / 2` blokkművelet után lesz meg.
- Törlés: a kereséshez hasonlóan.
- Beszúrás: a rekordok egyediségét biztosító mezőknek valóban egyedinek kell maradniuk. A beszúrás elvégzésekor vagy egy törölt rekord helyére lehet beírni az újat, vagy az állomány végére kell beszúrni (esetleg új blokkba).
- Módosítás: kb keresés + törlés + beszúrás jellemzőt hordozza. Minden esetben gondoskodni kell arról, hogy két megkülönböztethetetlen rekord ne kerüljön az adatbázisba.

### Hash-állományok

Ebben a megközelítésben egy rekord kulcsmezőiből vödrös hasheléssel megkapjuk a rekordot tartalmazó blokk címét tartalmazó vödröt.

Műveletek:

- Keresés: A hash függvényel megkapjuk azokat a blokkokat, amik potenciálisan tartalmazhatják a rekordot. Ezeket a blokkokat lineárisan végigolvasva megkapjuk a keresett rekordot. Ekkor az elérés ideje `1/(2B)` lesz, ahol `B` a hash függvény által használt vödrök száma.
- Beszúrás: az állomány beszúrása a keresésnek megfelelően történik (plusz egyediségi garanciák). Ha csak új blokkba lehet elhelyezni a beszúrt rekordot, akkor az új blokkot hozzá kell fűzni a megfelelő vödörben tárolt blokkokhoz.
- Törlés: beszúrás, csak fordítva
- Módosítás: ha nem érint kulcsmezőt, akkor semmi extra (mint a heap-ben). Ha viszont igen, akkor a vödör katalógust frissíteni kell, ami több műveletet is maga után vonhat (mivel lehet, hogy a rekordot csak új blokkba lehet beilleszteni).

### Indexelt állományok

Az alapötlet az, hogy a keresés kulcsát egy külön állományban tároljuk, ahonnan egy mutató a rekordot tartalmazó blokkra mutat. Az indexállományban a kulcsnak és a mutatónak fix mérete van, így az indexállomány `blocking_factor`a `f_i = floor(b / (k + p))` lesz, ahol `k` a kulcsmező mérete és `p` a mutató mérete.

Az indexelt állomány rendezve van tárolva.

Az indexállományoknak két gyakori típusa lehet:

- sűrű index: az indexállományban minden indexelt rekordhoz tartozik egy bejegyzés
- ritka index: csak az indexelt rekordok egy csoportjához rendel egy bejegyzést az indexállományban

### Ritka indexek

- Keresés: bináris kereséssel megkeressük a megfelelő bejegyzést az indexállományban, majd a mutatott blokkból kiolvassuk a keresett rekordot.
- Beszúrás: frissíteni kell az indexállományt.
- Törlés: frissíteni kell az indexállományt.
- Módosítás: Ha kulcsot érint a módosítás, egy beszúrás + törlés kombóval kell frissíteni az indexállományt.

### B*-fák

Alapötlet: az index is indexelve van: "Az i − 1. index egyidejűleg ritka indexe az i. indexnek és adatállománya az i − 2. indexnek".

![Fa szervezésű indexelés](assets/b-star-tree.png)



### Sűrű indexek, előnyök és hátrányok

Előnyök:

- nem kell rendezetten tartani az adatállományt
- támogatja a több kulcs szerinti keresést
- meggyorsíthatja a rekordelérést, mert a ritka index mérete jóval kisebb is lehet, mint sűrű index nélkül
- az adatállomány rekordjai (csaknem) szabadokká tehetők, ha minden további rekordhivatkozás a sűrű indexen keresztül történik (egyetlen mutatót kell megváltoztatni

Hátrányok:

- Sok helyet foglal
- +1 indirekció a rekord kiolvasásához
- karbantartási overhead

Műveletek: mintha egy hashtable-t használnánk

### Változó hosszúságú rekordok kezelése

(jegyzet: 3.4)

Ez a szituáció akkor állhat elő, ha egy mező változó hosszúságú lehet (pl egy név stringben), vagy ismétlődő mezőcsoport van egy rekordban. Általában a fix hosszúságú mezők a rekord elején, a változó hosszúságúak pedig a végén találhatóak, így a rekord eleje garantáltan fix hosszúságú marad. A változó hosszúságú mezők beillesztésére két megközelítés létezik: a konkrét adat egy pointerrel van helyettesítve, ami egy másik állományba mutat (így ez a mező is fix hosszúságúvá tehető), vagy a maximális lehetséges mennyiségű hely le van fogalva előre, és abba íródik az adat. Ezen kívül ennek a két megközelítésnek a hibridjét is lehet alkalmazni.

### Részleges információ alapján történő keresés

(jegyzet: 3.5)

(Feltételezzük, hogy a mezők egyike sem kulcs.)

Ebben az esetben az egyik megoldás, hogy több, vagy egyenesen minden mezőre építünk indexeket, és ez után sima indexelt keresésként kezeljük a problémát. Ez a megoldás elég költséges az indexek tárolása és karbantartása miatt.

Egy másik megoldás a partícionált hash függvények alkalmazása. Ennek alapötlete az, hogy a hash a rekord mezőiből külön külön van kalkulálva, úgy, hogy az összefűzött értéke a vöröd sorszámát adja. Ha egyes rekordok nem ismertek, az azokhoz tartozó bitminta "tetszőleges" lesz, és minden vödröt végig kell nézni, ahol passzolnak a hash ismert részei.

### Több kulcs szerinti keresés támogatása

Sűrű index használatával megvalósítható.

## A logikai adatbázis

### Adatmodellek, modellezés

Adatmodell:

- formalizált jelölésrendszer az adatok, adatkapcsolatok leírására
- műveletek az adatokon

Modellezés: a valóság leképzése valamilyen egyszerűsített formalizmusra

### Az E-R modell és elemei

Az ER modell nem teljes adatmodell, mivel az adatműveletek nincsek benne definiálva.

Elemei:

- Egyedtípusok
- Attribútumtípusok
- Kapcsolattípusok

#### Entitások (4.2.1.1)

> A valós világban létező, logikai vagy fizikai szempontból saját léttel rendelkező dolog, amelyről adatokat tárolunk.

Tulajdonságok

> Az entitásokat jellemzi, amelyen vagy amelyeken keresztül az entitások megkülönböztethetők.

Egyedhalmaz

> Az azonos attribútumtípusokkal jellem- zett egyedek összessége.

#### Kapcsolatok

> Entitások névvel ellátott viszonya.
>
> Kapcsolatok funcionalitása: pl. egy-egy, egy-több vagy több-több kapcsolat

#### Kulcs

> Az ER-modellezésnél az attribútumoknak azt a halma- zát, amely az entitás példányait egyértelműen azonosítja, kulcsnak nevezzük.

#### Gyenge egyedhalmaz

> ... a modellezés során egy entitáshalmaznak nem tudunk kulcsot meghatározni, hanem az egyedek azonosításához valamely kapcsolódó egyed(ek)re is szükség van. Ebben az esetben gyenge egyedhalmazról (weak entity set) beszélünk. A gyenge egyedhalmaz identitását egy (vagy ritkán több) ún. tulajdonos egyedhalmaz (owner entity set) biztosítja, amely a gyenge egyedhalmazzal több-egy kapcsolatban áll. A kapcsolat neve determináló kapcsolat (identifying relationship).

#### Grafikus ábrázolás

![Jelölések](assets/elements.png)

![Kapcsolatok](assets/relationships.png)

![Specializáció](assets/specialization.png)

![Gyenge egyedhalmaz](assets/weak_entity_set.png)

### A relációs adatmodell: adatok strukturálása és műveletek

#### Adatok strukturálása

Reláció: Halmazok Descartes-szorzatának részhalmaza. A relációban lévő attribútumok száma a reláció *foka*, a relációban lévő sorok száma pedig a reláció *számossága*.

Egy reláció nem tartalmazhat azonos sort, a sorok sorrendje nem számít, és az oszlopoknak egyértelmű nevük van.

#### Műveletek

- Únió: sorok értékei alapján
- Különbség: sorok értékei alapján
- Descartes-szorzat (Cartesian product) : Oszlopok nevei alapján
- Projekció
- Szelekció
- Természetes illesztés: ahol az azonos nevű attribútumok értékei megegyeznek
- Theta-illesztés: ugyanaz, mint a természetes illesztés, csak valamilyen feltételt lehet definiálni
- Hányados: kb Descartes-szorzat indexe

### Relációalgebra

Ugyanaz mint fent? 🤷‍♂️

### Sorkalkulus, oszlopkalkulus

(jegyzet 5.2, 5.3)

### Biztonságosság

Formula doménje: DOM(ψ) = { ψ-beli alaprelációk összes attribútumának értékei } U { ψ-ben előforduló konstansok }

{ *t* | ψ(*t*) } biztonságos, ha

- minden ψ(*t*)-t kielégítő *t* minden komponense DOM(ψ)-beli és
- ψ-nek minden (∃*u*)⍵(*u*) alakú részformulájára teljesül, hogy ha *u* kielégíti ⍵-t az ⍵-beli szabad változók valamely értéke mellett, akkor *u* minden komponense DOM(⍵)-beli

## Lekérdezés-optimalizálás

### Relációs lekérdezések heurisztikus optimalizálása

### Relációalgebraikifejezések transzformációi, ekvivalens kifejezések

### Relációs lekérdezések költségbecslés alapú optimalizálása

### Katalógusban tárolt információk

### A lekérdezés költsége: szelekció, indexelt szelekció, join műveletek és algoritmusok, egyéb műveletek

### Materializáció és pipelining

### A kiértékelési terv kiválasztása

## Adatbázisok logikai tervezése

### Relációs adatbázis sémák tervezése E-R diagramból

### Anomáliák (módosítási,  törlési, beszúrási)

### Adatbázis kényszerek, redundancia

### Funkcionális függőségek

### Relációs sémák kulcsai

### Armstrong axiómái a funkcionális függőségekről

### Az első normálforma (1NF)

### A második normálforma (2NF)

### A harmadik normálforma (3NF)

### A Boyce-Codd normálforma (BCNF)

## Tranzakció-kezelés

### ACID tulajdonságok adatbázis-kezelő rendszerekben

- **A**tomicity: Egy tranzakció vagy sikerül, vagy nem
- **C**onsistency: Egy művelet az adatbázist egy érvényes állapotból egy másik érvényes állapotba viszi át
- **I**solation: A párhuzamos tranzakciók is úgy futnak le, mintha egy másik tranzakció se futna rajtuk kívül
- **D**urability: Ha egy tranzakció sikeresen lefutott, annak hatása nem veszhet

### Ütemezések fajtái

- Soros ütemezés: a tranzakciók egyenként, egymás után futnak
- Nem soros ütemezés: minden más. Lehet sorosítható vagy nem sorosítható.

Sorosíthatóság:

> Egy ütemezés pontosan akkor so- rosítható, ha létezik olyan soros ütemezés (ez lesz a soros ekvivalens ütemezés, serial equivalent schedule), amelynek minden hatása a módosított adatokra azo- nos az adott ütemezésével.

### Lost update, non-repetable read, phantom read, dirty data

- Dirty read: Egy tranzakció olyan adatot olvas, amit egy másik tranzakció befejeződése előtt írt az adatbázisba
- Lost update: két tranzakció egy időben ír egy helyre, és a két update közül az egyiket felülírja a másik
- Non-repeatable read: ugyanarról a helyről két egymás utáni olvasás más eredményt ad, mert egy másik tranzakció a kettő között update-elte az adott adatot
- Phantom read: egy tranzakció többször ugyanazt a lekérdezést hajtja végre és különböző eredményhalmazokat kap vissza, mert közben egy másik tranzakció olyan adatokat szúr be, amik beleesnek a lekérdezés feltételébe

Izolációs elv:

> Egy tranzakció elvárt eredménye az, amit akkor kapunk, ha a tranzakció futása közben más tranzakció nem fut.

Korrekt ütemezés:

> Egy ütemezés akkor korrekt, ha sorosítható.

### Problémák a zárakkal: pattok és éhezés

Zár:

> Hozzáférési privilégium egy adategységen, amely adható és visszavonható.

Legális ütemezés:

> Legális az az ütemezés, amelyben
> 	– a lockolt adategységeket fel is szabadítják (unlockkal), továbbá
> 	– ha egy adategység már foglalt (mert egy másik tranzakció tart fenn zárat rajta, ami nem megosztható), akkor a tranzakció a zár felszabadulásáig várakozik.

#### Problémák:

##### Deadlock

Két tranzakció azért nem tud továbblépni, mert mindketten olyan zárat tartanak, ami a másiknak kell a továbblépéshez. Megoldási lehetőségek:

- A tranzakciók minden zárat egyszerre lockoljanak le, ha akármelyiket nem sikerül, azonnal térjenek vissza (valamilyen hibajelzéssel lehetőleg)
- Limitált ideig várakozzanak, és ha letelt a megadott várakozási idő anélkül, hogy megszerezték volna a szükséges zárat, azonnal térjenek vissza (valamilyen hibajelzéssel lehetőleg)
- A zárakat csak valamilyen előre definiált sorrendben lehessen megszerezni
- Egy "zármenedzser" folyamatosan figyelje a zárak elhelyezését, és ha ez a zármenedzser pattot érzékel, lője ki a pattot okozó tranzakciót

Várakozási gráf:

> Olyan irányított gráf, ahol a gráf csomópontjai a tranzakciók, egy élt pedig akkor rajzolunk az A csomópontból a B csomópont felé, ha az A tranzakció bármely okból várakoztatja a B tranzakciót úgy, hogy nem tud továbbmenni.

Ha egy adott időpontban nincs patt, a várakozási gráfban nincs kör, mivel

> Előre: (indirekt) tegyük fel, hogy van kör. Az élek rajzolásának szabálya miatt ez azt jelenti, hogy a körben résztvevő tranzakciók egymást várakoztatják, egyik sem tud továbblépni, ami éppen egy patthelyzetet jelent, ellentmondásban azzal, hogy nincs patt. Tehát ha nincs patt, akkor nem lehet kör a várakozási gráfban.
>
> Visszafelé: ha a gráf DAG, akkor létezik topologikus rendezése, ekkor pedig ez a tranzakcióknak egy olyan sorbarendezése, amelyben a tranzakciók sorban egymás után elindulhatnak anélkül, hogy várakoztatnák egymást. Tehát nincs patt.

### Tranzakció modellek

Egyszerű modell:

- csak egyfajta zár létezik
- egy adatelemen egy időben egy zár lehet

Sorosítási gráf az egyszerű modellben:

> Olyan irányított gráf, amelynek a csomópontjai a tranzakciók, egy élt pedig akkor rajzolunk a Ti csomópontból a Tj csomópont felé, ha van olyan A adategység, amelyen egy adott S ütemezésben a Ti tranzakció zárat helyezett el, majd a zár felszabadítása után először a Tj tranzakció helyez el zárat A-n.

RLOCK-WLOCK modell:

- Két fajta zár létezik:
  - RLOCK: Ha egy adott adategységen RLOCK van, más tranzakció olvashatja azt, de nem írhatja
  - WLOCK: Ha egy adott adategységen WLOCK van, semelyik másik tranzakció nem olvashatja vagy írhajta
- Az UNLOCK művelet mind a WLOCK-ot, mind a RLOCK-ot felszabadítja

Sorosítási gráf a RLOCK-WLOCK modellben:

A és B tranzakció között akkor kell élet rajzolni, ha

- A WLOCK-ot tart fenn és B ugyanarra az adatra akar RLOCK-ot tenni
- A akármilyen lockot tart fenn és B ugyanarra az adatra akar WLOCK-ot tenni

Egy S ütemezés akkor és csak akkor sorosítható, ha a sorosítási gráf irányított, aciklikus gráf (DAG), mivel

> Előre (indirekt): tegyük fel, hogy S sorosítható, de tartalmaz kört a sorosítási gráfja. Ekkor a kört alkotó tranzakciók közül egyik sem előzi meg a másikat, tehát egy soros ekvivalensben egyik sincs legelöl, azaz az ütemezés nem sorosítható, ellentmondásban a feltétellel.
>
> Visszafelé: ha a gráf DAG, akkor létezik topologikus rendezése. Belátjuk, hogy ebből a rendezésből legalább egy soros ekvivalens előállítható. Ugyanis a legelöl álló tranzakció (vagy tranzakciók) nem olvashat(nak) olyan adategységet, amin egy másik tranzakció korábban már zárat helyezett el, tehát először lefuthat(nak). Ha a gráfból eltávolítunk egy ilyen tulajdonságú tranzakciót (T_első) jelölő csomópontot, akkor a maradék gráf továbbra is DAG, tehát továbbra is létezik topologikus rendezése. A korábbi megfontolás továbbra is érvényes, így megadható(k) az(ok) a tranzakció(k), amelyek T_első után lefuthatnak, mert vagy egyáltalán nem olvas(nak) olyan adategységet, amin egy másik tranzakció korábban már zárat helyezett el, vagy csak T_első által már korábban lockolt adategységen helyeznek el zárat. Mindez addig folytatható, amíg a gráf minden csomópontját eltávolítottuk a gráfból: az eltávolítás sorrendje az előbbiek alapján az ütemezésnek egy soros ekvivalense lesz.

### Kétfázisú zárolás (2PL)

Az első zárfelszabadítást megelőzi mindegyik zárkérés.

Ha egy legális ütemezés a kétfázisú protokollt követi, az ütemezés sorosítható, mivel

> a sorosíthatóságnak szükséges és elégséges feltétele, hogy a sorosítási gráfban ne legyen kör, elegendő ezt belátni. ...

Zárpont: amikor egy kétfázisú protokollt követő tranzakció az utolsó zárját is megkapja.

Az előző tétel bizonyítása zárpontok segítségével:

> A tétel bizonyításához rendezzük a tranzakciókat a növekvő zárpontjuk szerinti sorrendbe. Beláthatjuk, hogy ez egy soros ekvivalens ütemezés lesz.
> Tegyük fel, hogy az ütemezésben a Ti: LOCK A után következik a Tj: LOCK A művelet (azaz minden soros ekvivalensben Ti meg kell, hogy előzze Tj-t). Ehhez nyilván az kell, hogy Ti felszabadítsa a zárat A-n (Ti: UNLOCK A), mielőtt Tj: LOCK A következne. Viszont Ti is kétfázisú, így meg kell hogy kapja minden zárját Tj: LOCK A előtt. Emiatt Ti biztosan megelőzi Tj-t a zárpontok növekvő sor- rendjében, valamennyi soros ekvivalensnek megfelelően. Így a növekvő zárpontok szerinti sorrend nem mond ellent a soros ekvivalens(eke)t meghatározó feltételeknek, azaz egyike a lehetséges soros ekvivalenseknek, az ütemezés sorosítható.

Az RLOCK-WLOCK modell kétfázisú, ha minden RLOCK és WLOCK megelőzi az első UNLOCK-ot.

### A fa protokoll

Akkor van jelentősége, ha az adategységek valamilyen hierarchikus struktúrába vannak szervezve, pl B* fa vagy egymásba ágyazott adatelemek.

A fa protokoll szabályai:

- A tranzakció akárhova teheti az első lockot
- további lockot csak arra az adatra lehet helyezni, aminek a szűlőjére ugyanaz a tranzakció már rakott zárat
- egy tranzakció kétszer nem zárolhatja ugyanazt az adatot.

Mivel az unlockra nincs előírás, a protokoll nem feltétlenül kétfázisú.

A fa protokollnak eleget tevő legális ütemezések sorosíthatóak, mivel (jegyzet 10.6.1 bizonyítás).

### A figyelmeztető protokoll

### Tranzakcióhibák kezelése, commit pont

### Szigorú kétfázisú protokoll (szigorú 2PL)

### Agresszív és konzervatív protokollok

### Védekezés rendszerhibák ellen

### Hatékonysági kérdések

### A redo protokoll: naplózás és helyreállítás

### Ellenőrzési pontok (checkpointing)

### Időbélyeges tranzakciókezelés R/W modellben

### Az időbélyeges R/W modell és a 2PL összehasonlítása

### Tranzakcióhibák és az időbélyegek

### Verziókezelés időbélyegek mellett (MVCC)
