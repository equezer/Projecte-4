# Projecte04: Servidor NFS

## El Cas Client: DevOptimize Solutions

El nostre client, DevOptimize Solutions, és una petita startup de desenvolupament de programari que treballa exclusivament amb Linux. Tenen un problema crític: el seu codi font i els seus actius (documents de disseny, scripts) estan descontrolats. Cada desenvolupador té còpies locals, cosa que provoca errors de versió constants i una pèrdua d'eficiència brutal. Ens han contractat per implementar un servidor de fitxers centralitzat. Atès que tot l'entorn és Linux, la solució nativa, més ràpida i eficient del sector és NFS (Network File System). El client ha insistit en que treballa sense un entorn d’autenticació centralitzada i que, de moment, no té previst fer aquest pas.

Per mostrar al client com quedarà la solució proposada a partir de les seves demandes i poder mostrar també les seves limitacions, se t’encarrega fer una demostració del sistema.

Crearàs un servidor NFS (NFSv3) i un client Linux que consumeixi els recursos compartits. Hauràs de crear usuaris i grups per simular l'entorn del client i demostrar el control d'accés utilitzant les opcions d'exportació (/etc/exports) i els permisos del sistema de fitxers (chmod, chown).


## Fase 2: Preparació del servidor

Abans de compartir res, hem de preparar els usuaris i els directoris al Servidor.

### 1. Creació de Grups: Crear dos grups per al client: devs i admins.

primer al servidor Ubuntu creearem aquests dos grups

```bash
sudo groupadd devs
```
<img width="605" height="30" alt="image" src="https://github.com/user-attachments/assets/23df9f8d-ffc3-490b-9617-504129d3e09c" />

```bash
sudo groupadd admins
```

<img width="638" height="26" alt="image" src="https://github.com/user-attachments/assets/76bbda13-98b4-49f4-b9ca-931301f6c11a" />

---

### 2. Creació d'Usuaris: Crear un usuari dev01 (membre del grup devs).

creem l'usuari amb la contrasenya que serà: usuari

```bash
sudo useradd -m dev01
```
<img width="666" height="23" alt="image" src="https://github.com/user-attachments/assets/26d92152-931f-4c93-a892-141ff5d91be9" />

```bash
sudo passwd dev01
```
<img width="622" height="152" alt="image" src="https://github.com/user-attachments/assets/95a1bcf1-f591-41b0-9089-c7be5443d351" />

```bash
sudo usermod -aG devs dev01
```

---

### 3. Crear un usuari admin01 (membre del grup admins). Creació de Directoris (al Servidor):

```bash
sudo useradd -m admin01
sudo passwd admin01
```
<img width="697" height="161" alt="image" src="https://github.com/user-attachments/assets/1a29a877-cfff-411f-8532-2d7a812d85ae" />

```bash
sudo usermod -aG admins admin01
```
<img width="719" height="31" alt="image" src="https://github.com/user-attachments/assets/1ea9af03-a2ea-496b-8ea6-77f0b122db74" />

---

### 4. Crear el directori per als projectes de desenvolupament: /srv/nfs/dev_projects

```bash
sudo mkdir -p /srv/nfs/dev_projects
```

<img width="771" height="28" alt="image" src="https://github.com/user-attachments/assets/063a103f-fbbb-4aa4-92ae-621f265a3b25" />

---
  
### 5. Crear el directori per a les eines d'administració: /srv/nfs/admin_tools

```bash
sudo mkdir -p /srv/nfs/admin_tools
```
<img width="766" height="27" alt="image" src="https://github.com/user-attachments/assets/0e426340-0046-4d61-b95d-207a03707928" />

---

### 6. Permisos del Servidor (El punt clau):

- Es vol que els developers tinguin control total sobre els seus projectes.

<img width="744" height="22" alt="image" src="https://github.com/user-attachments/assets/7c21eaa5-c26f-441c-b387-355f5e5df9af" />

<img width="687" height="22" alt="image" src="https://github.com/user-attachments/assets/3f2543e9-9d3f-4706-a83c-37d1ba0b6cdc" />

- Es vol que els administradors tinguin control sobre les seves eines.

<img width="759" height="23" alt="image" src="https://github.com/user-attachments/assets/cbb00eea-0f3c-4710-bda5-c0ae3189c1c3" />

<img width="673" height="22" alt="image" src="https://github.com/user-attachments/assets/147d91a6-876b-4539-8fe5-ae2281533c4d" />

---

- Com a pas final, s'instal·laran els paquets necessaris per al servei NFS al servidor i es configurarà l'exportació dels directoris amb les opcions adequades.

```bash
sudo apt install nfs-kernel-server
```

<img width="648" height="16" alt="image" src="https://github.com/user-attachments/assets/d23f70f6-2b14-43e9-9990-42d73a28d697" />

---

Al servidor, caldrà instal·lar el client nfs:

```bash
sudo apt install nfs-common
```

<img width="812" height="324" alt="image" src="https://github.com/user-attachments/assets/ff0701db-4efb-42cf-8e8c-13c2778d0257" />

---

Un cop fet això en conectarem al servidor amb la comanda showmount amb la ip que ens toqui

```bash
showmount -e 192.168.67.67
```
<img width="559" height="71" alt="image" src="https://github.com/user-attachments/assets/282b2d16-7286-4b48-a8a9-8b0472615719" />

---

# Fase 3: L'Exportació d'Administració (El Dilema del root_squash)

## Prova 1 (L'error comú)

### 1. Entrarem al arxiu de /etc/exports al client i afegirem la configuració necessaria afegint: "no_root_squash"

<img width="604" height="37" alt="image" src="https://github.com/user-attachments/assets/dcb590b2-7880-4a73-979e-057acba22960" />

<img width="630" height="210" alt="image" src="https://github.com/user-attachments/assets/199a8afa-5032-4ef5-b255-27a5c475444a" />

---

### 2. Crearem el directori de /mnt/admin_tools al client i després muntarem el recurs fns al servidor

<img width="699" height="23" alt="image" src="https://github.com/user-attachments/assets/d62ed26f-2fff-4eae-8f7d-17ede1172a8f" />

<img width="748" height="16" alt="image" src="https://github.com/user-attachments/assets/8d78e9ec-046e-413e-952e-41470d991c9d" />

---

### 3. Verifiquem que està muntat correctament al servidor amb aquesta comanda:

```bash
mount | grep admin_tools
```
<img width="959" height="53" alt="Captura de pantalla 2025-12-04 173216" src="https://github.com/user-attachments/assets/a1be6a8f-8d12-4164-a650-cae962a0a6a4" />

---

### 4. Un cop fet això podrem crear un nou arxiu, per exemple en aquest cas he creat una arxiu anomenat adminjan

```bash
sudo touch /mnt/admin_tools/adminjan.txt
```
<img width="887" height="578" alt="Captura de pantalla 2025-12-11 200432" src="https://github.com/user-attachments/assets/dc61ee95-9c5d-490f-a5d5-90f7afe9453e" />

---

# Fase 4: L'Exportació de Desenvolupament (Permisos rw vs ro)

el client ens demana el seguent la xarxa d'administració (p.ex., 192.168.56.0/24) hi pugui escriure, però que la xarxa de consultors (p.ex., 192.168.56.100) només pugui llegir.

### 1. Primer  haurem de modificar l'arxiu /etc/exports i substituir la linia "/srv/nfs/dev_projects *(rw,sync,no_subtree_check)" 

```bash
sudo nano /etc/exports
```
<img width="727" height="242" alt="Captura de pantalla 2025-12-11 201152" src="https://github.com/user-attachments/assets/6107e7a9-8662-44bc-91b1-0e8c7b2c80a2" />

---

Tot seguit reinciem el servei amb la comanda:

```bash
systemctl restart nfs-kernel-server
```

<img width="537" height="63" alt="Captura de pantalla 2025-12-11 201352" src="https://github.com/user-attachments/assets/48c93bd1-c572-4afe-b170-fb826fc9acbd" />

---

### 2. Ara al client muntar el recurs compartit a /mnt/dev_projects

creem la carpeta indicat a la tasca:

<img width="564" height="21" alt="image" src="https://github.com/user-attachments/assets/1675cb30-d1d6-4d99-9d5b-134187db1d9e" />

---

Intentarem escriure com usuari dev01 i no ens deixarà per la configuracio que haurem de fer ara:

<img width="614" height="18" alt="image" src="https://github.com/user-attachments/assets/9c5cb427-8074-4a40-97e0-b9375be198f7" />

---

modificarem la nostre ip, en aquest cas probarem amb la ip 192.168.56.100 per poder fer això anirem a la configuració de xarxa i colocarem la ip manualment i muntarem el disc


<img width="936" height="656" alt="Captura de pantalla 2025-12-11 203020" src="https://github.com/user-attachments/assets/8c05e6a0-8c3c-4b8d-b8e9-af988481670e" />

---

si fem login l'usuari dev01 com que tenim una ip dins del rang que pot editar dins de la carpeta si que podrem crear arxius

<img width="457" height="19" alt="Captura de pantalla 2025-12-11 203758" src="https://github.com/user-attachments/assets/5fa86042-7815-4fa5-b960-e6e5f2a8a22d" />

<img width="378" height="37" alt="Captura de pantalla 2025-12-11 205346" src="https://github.com/user-attachments/assets/c2d62ba3-d265-4220-af30-2afff1b938a1" />

---

Canvieu d'usuari al client a admin01 i torneu a provar d'escriure al directori muntat i no ens deixarà escriure

<img width="434" height="18" alt="Captura de pantalla 2025-12-11 205915" src="https://github.com/user-attachments/assets/b671f92d-7900-4bc9-be6d-1c785d1d54dd" />
<img width="697" height="18" alt="Captura de pantalla 2025-12-11 205951" src="https://github.com/user-attachments/assets/e2a0b037-ad32-4650-8b41-19e00a78d649" />

---

# Fase 5: Muntatge Automàtic amb /etc/fstab

### 1. Modificarem l'arxiu /etc/fstab per poder configurar que els recursos compartits no es tinguin que muntar cada vegada que entrem

<img width="513" height="21" alt="Captura de pantalla 2025-12-11 211519" src="https://github.com/user-attachments/assets/d37f1b42-57a8-43c6-b5a9-f8819aa2f53a" />

<img width="782" height="283" alt="Captura de pantalla 2025-12-11 211535" src="https://github.com/user-attachments/assets/75b6bf80-2fb9-4ecb-a02a-97eb7877de57" />

---

### 2. I per últim fem la comanda mount -a per provar les entrades sense reiniciar

<img width="457" height="19" alt="Captura de pantalla 2025-12-11 211828" src="https://github.com/user-attachments/assets/64abb3ab-4796-4612-a531-63d1b0565b9e" />

i ho comprovem amb:

<img width="478" height="19" alt="Captura de pantalla 2025-12-11 212227" src="https://github.com/user-attachments/assets/dc7dbf9a-dc77-4a7a-9d85-05ab7478f378" />

---

### 3. Reiniciar i verificar

<img width="322" height="17" alt="Captura de pantalla 2025-12-15 201139" src="https://github.com/user-attachments/assets/8e365b4f-4dde-4e06-9c20-25b6879829d4" />

---

I per ultim comprova que s’han muntat automàticament:

```bash
mount | grep /mnt/admin_tools
```
```bash
mount | grep /mnt/dev_projects
```

[torna a la pàgina principal](../README.md)
