# Fogalmak

## Adatbázisok logikai tervezése

<details>
  <summary>Redundáns reláció</summary>
  Ha egy relációban valamely attribútum értékét a relációban található más attribútum(ok) értékéből ki tudjuk következtetni valamely ismert következtetési szabály segítségével, akkor a relációt redundánsnak nevezzük.
</details>

<details>
  <summary>Teljes függés</summary>
  Ha X, Y ⊆ R és X → Y , de ∄X′ ⊂ X, hogy X′ → Y, akkor azt mondjuk, hogy Y teljesen függ (funkcionálisan) X-től.
</details>

<details>
  <summary>Igaz funkcionális függés</summary>
Egy adott R sémán az attribútumain értelmezett FR függéshalmaz mellett egy X → Y függőség pontosan akkor igaz, ha minden olyan r(R) reláción fennáll, amelyeken FR összes függősége is fennáll.
</details>



## Tranzakció-kezelés

<details>
 <summary>Tranzakció/Atomi művelet</summary>
  Egy program egyszeri futása, amelynek vagy minden művelete hatásos, vagy egyik se.</details>

<details>
  <summary>Ütemezés</summary>
  Tranzakciók elemi műveleteinek összessége, melyben a műveletek időbeli sorrendje is egyértelműen meghatározott.
</details>

<details>
  <summary>Izolációs elv</summary>
  Feltételezzük, hogy egy tranzakció elvárt, korrekt eredménye az, amit akkor kapunk, ha a tranzakció futása közben más tranzakció nem fut.
</details>

<details>
  <summary>Várakozási gráf</summary>
  Olyan irányított gráf, ahol a gráf csomópontjai a tranzakciók, egy élt pedig akkor rajzolunk a Ti csomópontból a Tj csomópont felé, ha a Ti tranzakció bármely okból várakoztatja a Tj tranzakciót úgy, hogy az nem tud továbbmenni.
</details>

<details>
  <summary>Zár</summary>Hozzáférési privilégium egy adategységen, amely adható és visszavonható.
</details>

<details>
  <summary>Sorosítási gráf, precedenciagráf</summary>
  Olyan irányított gráf, amelynek a csomópontjai a tranzakciók, egy élt pedig akkor rajzolunk a Ti csomópontból a Tj csomópont felé, ha van olyan A adategység, amelyen egy adott S ütemezésben a Ti tranzakció zárat helyezett el, majd a zár felszabadítása után először a Tj tranzakció helyez el zárat A-n.
</details>

<details>
  <summary>Zárpont</summary>
  Az az időpont, amikor egy kétfá- zisú protokoll szerinti tranzakció az utolsó zárját is megkapja.
</details>

<details>
  <summary>Konzisztens állapot</summary>
  Az adatbázisnak olyan állapota, amely csak teljesen lefutott tranzakciók hatását tükrözi (ld. ACID tulajdonságok)
</details>

<details>
  <summary>Commit pont</summary>
  Az az időpillanat, amikor egy tranzakció futása során már minden befejeződött, ami a tranzakció 1-3. okok miatti abortját eredményezheti.
</details>

<details>
  <summary>Dirty data</summary>
  Olyan adat, amit az előtt írt valamely tranzakció az adatbázisba, mielőtt commitált volna.
</details>

<details>
  <summary>Napló</summary>
  A napló a mi értelmezésünk szerint az adat- bázison végrehajtott változások története.</details>

<details>
  <summary>Időbélyeg</summary>
  Olyan érték, amelyet minden tranzakcióhoz szigorú egyediséget biztosítva rendelünk hozzá, és amely arányos (legegyszerűbb esetben azonos) a tranzakció kezdőidejével. Jele: t(Tranzakció).
</details>

