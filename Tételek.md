# Tételek

## Logikai adatbázis

- A sor/oszlopkalkulus kifejezőereje legalább akkora, mint a relációs algabráé (visszafelé nem igaz, mert a relációs algebrában nem lehet negálni)
- Minden relációs algebrai kifejezést át lehet alakítani ekvivalens sorkalkulus kifejezéssé
- Minden relációs algebrai kifejezést át lehet alakítani ekvivalens oszlopkalkulus kifejezéssé

## Adatbázisok logikai tervezése

- Minden relációs sémának van kulcsa.
- 

## Tranzakciókezelés

- Egy S ütemezés sorosítható ⇔ a sorosítási gráf DAG.
- Ha egy legális ütemezés minden tranzakciója a 2PL protokollt követi, akkor az ütemezés sorosítható.
- Egy RLOCK-WLOCK modellbeli S ütemezés sorosítható ⇔ a fenti szabályok szerint rajzolt sorosítási gráf DAG.
- Ha egy ütemezésben csak kétfázisú, RLOCK-WLOCK modell szerinti tranzakciók vannak, akkor az ütemezés sorosítható.
- A fa protokollnak eleget tevő legális ütemezések sorosíthatók.
- A figyelmeztető protokollt követő legális ütemezések zárkonfliktusmentesek (1) és sorosíthatók (2).
- A szigorú kétfázisú protokollt követő tranzakciókból álló legális ütemezések sorosíthatók és lavinamentesek.

