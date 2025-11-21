# T02: DPR: còpies de seguretat. Cas pràctic

# Introducció al cas

A la tasca anterior heu dissenyat una política de còpies de seguretat pel nostre nou client **"Muntatges i Serveis Tècnics SL"**. Ara toca passar a l’acció i portar a la pràctica l’estudi anterior. El client demana que s’elaborin unes guies tècniques amb proves de concepte per tal que el seu personal estigui qualificat per implantar el pla de còpies de seguretat.

---

## Part 1: Còpia de seguretat dels equips clients Windows

Encara que en principi el DPR no contemplaria fer còpia dels arxius locals dels equips clients, se’ns demana fer una excepció amb l’equip Windows del director de l’empresa. En aquest equip es guarda informació important que no es vol tenir accessible al servidor de fitxers de l’empresa. Per aquest motiu és necessari definir una política de còpies de seguretat seguint l’esquema **3-2-1**:  
- es farà una còpia de seguretat a un disc secundari que té el propi equip  
- i una segona còpia al **cloud (Google Drive)** usant l’eina **Duplicati**.

Com a prova de concepte per crear la guia, creareu una màquina virtual **Windows 11** amb dos discos:  
- un per instal·lar el sistema operatiu  
- i un segon disc de **10 GB** per emmagatzemar les còpies de seguretat.

Per simular la part de Google Drive, useu un compte que **no sigui el de l’escola** (podeu crear un compte específic per l’activitat).

Es desitja fer còpies de seguretat del perfil de l’usuari **cada hora** al disc secundari i a les **18:00** a Google Drive.

Heu de documentar:  
- el procediment d’instal·lació de Duplicati  
- la configuració dels plans de còpies  
- i observar-ne el funcionament  

Per això, afegiu arxius a les carpetes de l’usuari, especialment a **Documents**.

1. Esborreu el contingut de *Documents* i procediu a fer una restauració des del disc secundari.  
2. Comproveu com podeu fer una restauració des de la còpia que teniu emmagatzemada al cloud.

---

## Part 2: Còpia de seguretat del servidor Linux

Per fer les còpies del servidor Linux, la solució proposada pel vostre responsable és **Duplicity**, que permet fer còpies tant contra un mitjà local com un servidor remot. Combinat amb el programador de tasques (**cron**), es poden implementar les polítiques de còpia que es desitgin.

Has de crear una guia tècnica per explicar com es pot usar aquesta eina per fer còpies d’un servidor Linux.

Com a prova de concepte, usaràs una màquina virtual amb un **Ubuntu Server** instal·lat i li afegiràs un segon disc de **10 GB** que simularà una unitat auxiliar.


a l'arxiu: [solucio.md](solucio.md) trobaras la solució a la tasca

[torna a la pàgina principal](../README.md)


