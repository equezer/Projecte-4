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

---

# T01: Còpies de seguretat — Part 2

Autors: Jan Fernández, Pol Castaño

## Fase 2: Treball per parelles

Treballant per parelles:

Discussió i Consens: Compareu les vostres respostes individuals (Fase 1).

Elaboració d'una Proposta Unificada: Heu de consensuar i dissenyar el vostre propi Esquema 3-2-1 de còpies (3 còpies, 2 mitjans, 1 fora de lloc) basat en els requisits del cas.

Proposta de la Parella
| Element                 | Proposta          | Justificació                                                                                |
| ----------------------- | ----------------- | ------------------------------------------------------------------------------------------- |
| **Dades Crítiques**     | NAS local         | Per recuperacions ràpides                                                                   |
| **Periodicitat (BD)**   | Diàriament        | Utilitzarem còpies diàries                                                                  |
| **Tipus de Còpia (BD)** | Incremental (NAS) | Es faran còpies diàries incrementals cada 4 hores                                           |
|                         | Completa (CLOUD)  | Farem còpies completes setmanals; es faran els diumenges                                    |
| **Mitjà 1 (Local)**     | NAS               | El NAS és molt efectiu per poder recuperar informació de manera ràpida en cas de necessitat |
| **Mitjà 2 (Extern)**    | Cloud             | Cal tenir un mitjà completament fora de l'empresa                                           |

---

# T01: DRP – Còpies de Seguretat part 3

Estudi cas client
Autors: Jan Fernandez, Pol Castaño, David Ballesteros i Christian Bogdanas

## Proposta de Còpies – Muntatges i Serveis Tècnics SL

## Dades Objecte còpies

| Origen                                                | Dades Crítiques            | Freqüència de còpia                                                  |
| ----------------------------------------------------- | -------------------------- | -------------------------------------------------------------------- |
| **Servidor Bases de Dades (Comptabilitat i Clients)** | Sí                         | Incremental cada 4 h + Completa diària; Completa setmanal (diumenge) |
| **Servidor Documents de Projectes**                   | No                         | Incremental diària + Completa setmanal                               |
| **Servidor Carpetes Personals dels Usuaris**          | No                         | Incremental diària + Completa setmanal                               |
| **Clients – Carpeta “Documents”**                     | Sí/No (segons importància) | Incremental diària + Completa setmanal                               |

Justificació

Les bases de dades són crítiques perquè tenen canvis constants i només es poden permetre perdre un màxim de 4 hores de dades.
Els Documents de Projectes i Carpetes Personals són importants però poden tolerar fins a 24 hores de pèrdua.
La carpeta “Documents” dels clients es copia parcialment, ja que alguns tècnics hi deixen informació rellevant.

## 2) Cronograma Setmanal Detallat

| Dia           | Dades                  | Tipus de Còpia                         | Mitjà           |
| ------------- | ---------------------- | -------------------------------------- | --------------- |
| **Dilluns**   | Bases de Dades         | Incremental cada 4 h + Completa diària | NAS             |
|               | Documents de Projectes | Incremental                            | NAS             |
|               | Carpetes Personals     | Incremental                            | Disc Dur Extern |
| **Dimarts**   | Bases de Dades         | Incremental cada 4 h + Completa diària | NAS             |
|               | Documents de Projectes | Incremental                            | NAS             |
|               | Carpetes Personals     | Incremental                            | Disc Dur Extern |
| **Dimecres**  | Bases de Dades         | Incremental cada 4 h + Completa diària | NAS             |
|               | Documents de Projectes | Incremental                            | NAS             |
|               | Carpetes Personals     | Incremental                            | Disc Dur Extern |
| **Dijous**    | Bases de Dades         | Incremental cada 4 h + Completa diària | NAS             |
|               | Documents de Projectes | Incremental                            | NAS             |
|               | Carpetes Personals     | Incremental                            | Disc Dur Extern |
| **Divendres** | Bases de Dades         | Incremental cada 4 h + Completa diària | NAS             |
|               | Documents de Projectes | Incremental                            | NAS             |
|               | Carpetes Personals     | Incremental                            | Disc Dur Extern |
| **Dissabte**  | Bases de Dades         | Incremental cada 4 h + Completa diària | NAS             |
|               | Documents de Projectes | Incremental                            | NAS             |
|               | Carpetes Personals     | Incremental                            | Disc Dur Extern |
| **Diumenge**  | Bases de Dades         | Completa setmanal                      | Cloud           |
|               | Documents de Projectes | Completa setmanal                      | Cloud           |
|               | Carpetes Personals     | Completa setmanal                      | Cloud           |

## 3) Elecció de Mitjans i Ubicació (Regla 3-2-1)

Mitjà 1 (Local)

NAS intern

Justificació:
Permet restaurar dades ràpidament. És el suport principal per a còpies diàries i incrementals.

Mitjà 2 (Extern)

Cloud Backup
(Google Cloud o Backblaze B2 recomanats)

Justificació:
Proporciona còpia fora de l’empresa amb alta disponibilitat i seguretat.
Els discs durs externs reforcen la seguretat setmanalment.

Ubicació Fora de Lloc

Les còpies al Cloud es guarden fora de l’empresa.

Els discs durs externs es poden guardar en un altre despatx o arxiu segur.

Responsable: El tècnic IT revisa sincronització, completitud i historial de còpies.

## 4) Estratègia de Recuperació (RTO/RPO)

RPO – Pèrdua de dades admissible

Bases de dades: pèrdua màxima de 4 hores gràcies a les incrementals cada 4 h.

RTO – Temps màxim de recuperació

Recuperació des del NAS en menys de 4 hores.

Còpies al Cloud o discs externs garantitzen recuperació fins i tot en cas de pèrdua total de l’equip físic.

## Conclusió

Amb aquesta estratègia de còpies i ubicacions, es compleixen tots els requisits de la regla 3-2-1, minimitzant el risc de pèrdua de dades i assegurant la disponibilitat dins dels temps màxims permesos.
