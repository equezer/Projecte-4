# **T01: DRP: còpies de seguretat. Estudi cas client (treball cooperatiu)**

 

**Fase 1: Treball individual**

De forma individual, heu de donar resposta a les següents preguntes basant-se en el cas pràctic:

1\.       Què copiar? (Priorització): Quines són les dades més crítiques del servidor? Cal fer còpia dels 10 equips clients? Justifica-ho.

les dades més crítiques del servidor son els documents de projectes ja que poden contenir informació molt important de l’empresa i les  Carpetes Personals dels Usuaris per la mateixa raó. No faria falta fer una còpia dels 10 equips clients.

2\. Periodicitat i Tipus de Còpia: Proposa un calendari bàsic per a la setmana (Diari/Setmanal/Mensual) i quin tipus de còpia aplicaràs (Completa, Diferencial, Incremental) per a les dades crítiques.

| Calendari Setmanal |  |  |  |
| ----- | :---- | :---- | :---- |
|  | Completa  | Diferencial | Incremental |
| Dilluns |  |  | Incremental diària \+ increments BBDD cada 4 h |
| Dimarts |  |  | Incremental diària \+ increments BBDD cada 4 h |
| Dimecres |  |  | Incremental diària \+ increments BBDD cada 4 h |
| Dijous |  |  | Incremental diària \+ increments BBDD cada 4 h |
| Divendres |  |  | Incremental diària \+ increments BBDD cada 4 h |
| Dissabte |  |  | Incremental diària \+ increments BBDD cada 4 h |
| Diumenge | Completa setmanal (totes les dades) |  | Incremental BBDD cada 4 h |

- Incrementals diaris per a documents, carpetes d’usuari i equips clients.

- Incrementals cada 4 hores per a les bases de dades de Comptabilitat

- Completa setmanal el diumenge per tenir un punt base fiable per a restauracions completes.

- No s’utilitza còpia diferencial perquè incrementals \+ completa setmanal és més eficient en espai i compleix requisits.

3\.   Mitjans i Ubicació: Quin tipus de mitjà de còpia utilitzaries (Discs durs externs, NAS, Cloud, Cintes)? On s'hauria de guardar físicament la còpia més recent (Regla 3-2-1).

**Mitjans de còpia utilitzats:**

- NAS local per les còpies incrementals i recuperacions ràpides.

- Cloud per a les còpies completes setmanals i retencions mensuals, assegurant una còpia fora de l’empresa.

- Disc dur extern com a còpia offline per reforçar la seguretat contra ransomware.

