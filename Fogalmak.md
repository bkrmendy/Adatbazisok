# Fogalmak

<details>
 <summary>Tranzakció/Atomi művelet</summary>
  Egy program egyszeri futása, amelynek vagy minden művelete hatásos, vagy egyik se.</details>

<details>
  <summary>ACID</summary>
  - atomicitás (atomicity): ld. fentebb.

	- konzisztencia (consistency): csak sikeresen (teljes egészében) lefutott tranzakcióknak van hatása az adatbázis tartalmára, ekkor a tranzakciók az adatbázist egyik konzisztens állapotból egy másikba viszik át. 
	  
	- izoláció (isolation), másnéven elszigetelés: minden tranzakció úgy fut le (egy konkurens környezetben is), mintha közben más tranzakció nem futna.

  - tartósság (durability): ha egy tranzakció már sikeresen lefutott, akkor annak hatása nem veszhet el.
</details>

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

