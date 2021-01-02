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





