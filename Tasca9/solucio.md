# Projecte04: Servidor NFS

## El Cas Client: DevOptimize Solutions

El nostre client, DevOptimize Solutions, és una petita startup de desenvolupament de programari que treballa exclusivament amb Linux. Tenen un problema crític: el seu codi font i els seus actius (documents de disseny, scripts) estan descontrolats. Cada desenvolupador té còpies locals, cosa que provoca errors de versió constants i una pèrdua d'eficiència brutal. Ens han contractat per implementar un servidor de fitxers centralitzat. Atès que tot l'entorn és Linux, la solució nativa, més ràpida i eficient del sector és NFS (Network File System). El client ha insistit en que treballa sense un entorn d’autenticació centralitzada i que, de moment, no té previst fer aquest pas.

Per mostrar al client com quedarà la solució proposada a partir de les seves demandes i poder mostrar també les seves limitacions, se t’encarrega fer una demostració del sistema.

Crearàs un servidor NFS (NFSv3) i un client Linux que consumeixi els recursos compartits. Hauràs de crear usuaris i grups per simular l'entorn del client i demostrar el control d'accés utilitzant les opcions d'exportació (/etc/exports) i els permisos del sistema de fitxers (chmod, chown).


## Fase 2: Preparació del servidor

Abans de compartir res, hem de preparar els usuaris i els directoris al Servidor.

1. Creació de Grups: Crear dos grups per al client: devs i admins.

primer al servidor Ubuntu creearem aquests dos grups

  ```bash
sudo groupadd devs
```
```bash
sudo groupadd admins
```

3. Creació d'Usuaris: Crear un usuari dev01 (membre del grup devs).

creem l'usuari amb la contrasenya que serà: usuari

```bash
sudo useradd -m dev01
sudo passwd dev01
```

5. Crear un usuari admin01 (membre del grup admins). Creació de Directoris (al Servidor):

6. Crear el directori per als projectes de desenvolupament: /srv/nfs/dev_projects

7. Crear el directori per a les eines d'administració: /srv/nfs/admin_tools

8. Permisos del Servidor (El punt clau):

- Es vol que els developers tinguin control total sobre els seus projectes.
- Es vol que els administradors tinguin control sobre les seves eines.
- En tots dos casos, l'usuari propietari serà root.
- Com a pas final, s'instal·laran els paquets necessaris per al servei NFS al servidor i es configurarà l'exportació dels directoris amb les opcions adequades.
