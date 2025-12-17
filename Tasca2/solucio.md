# T02: DPR – Còpies de seguretat  
## Cas pràctic

---

## Part 1: Còpia de seguretat dels equips clients Windows

### 1. Afegim un disc de 10 GB
Afegim un disc de **10 GB** que serà el disc de *backup*.

<img width="542" height="304" alt="image" src="https://github.com/user-attachments/assets/7ed324b4-2b52-4dcf-acbb-868514385b21" />

---

### 2. Obrim l’administrador de discos
Obrim l’administrador de discos i creem un **disc simple nou**.

<img width="544" height="255" alt="image" src="https://github.com/user-attachments/assets/deda2b76-4202-4c48-9068-6d0adba91155" />

<img width="541" height="178" alt="image" src="https://github.com/user-attachments/assets/016ca7a9-9155-4fee-996f-94575689560e" />

<img width="541" height="153" alt="image" src="https://github.com/user-attachments/assets/f82df57d-5454-43b1-be6e-bf558e45b6cf" />

---

### 3. Instal·lació de Duplicati
Obrim la màquina de **Windows 11** i anem al **Microsoft Edge** per instal·lar i configurar **Duplicati**.

<img width="538" height="379" alt="image" src="https://github.com/user-attachments/assets/8dc8a9d2-ff8d-4ffe-ba37-cc700d2df1dd" />


---

### 4. Contrasenya de seguretat
Un cop instal·lat, ens demanarà crear una contrasenya per seguretat.  

<img width="752" height="527" alt="image" src="https://github.com/user-attachments/assets/7a755147-f7c3-4374-b208-5c15e8c56f05" />

---

### 5. Creació del pla de còpia local (cada hora)

#### Crear Backup 1: Local
Afegim un **backup nou**.

<img width="659" height="329" alt="image" src="https://github.com/user-attachments/assets/dda10b72-740f-4fd2-b9e4-35b3037f9445" />

<img width="443" height="515" alt="image" src="https://github.com/user-attachments/assets/a97f7d40-23aa-4581-a14c-9d0acb472e9c" />


Configurem el nou backup.

<img width="541" height="454" alt="image" src="https://github.com/user-attachments/assets/f1f4c8b2-c8f0-4b44-8bd1-38d1f525ca7a" />


---

#### Destinació del backup
Indiquem la destinació on anirà el nostre backup (disc secundari).

<img width="597" height="498" alt="image" src="https://github.com/user-attachments/assets/7aa6053a-ef01-4363-8a0b-59e6473ce222" />


---

#### Dades d’origen
A l’apartat de dades d’origen seleccionem:
- La carpeta creada anteriorment
- Un nou *path* anomenat `backups`

<img width="751" height="463" alt="image" src="https://github.com/user-attachments/assets/bc9c083a-cee7-4f7d-a48b-d97a271a208f" />


---

#### Planificació
Configurem el backup perquè:
- Es faci **cada hora**
- Comenci a les **13:00**

<img width="469" height="441" alt="image" src="https://github.com/user-attachments/assets/4bff13ef-1514-4623-96cb-6edfe24ae714" />

Un cop fet això, ja tindrem el **backup local creat**.

<img width="751" height="452" alt="image" src="https://github.com/user-attachments/assets/84415042-63e6-48a3-9db2-f951381e3786" />


---

## Còpia de seguretat al núvol (Google Drive)

Creem una còpia de seguretat al núvol amb **Google Drive**, repetint el procés fins a l’apartat de destinació del backup.

1.
<img width="463" height="144" alt="image" src="https://github.com/user-attachments/assets/a503f767-4eee-466d-b85f-6c193998d428" />
2.
<img width="356" height="416" alt="image" src="https://github.com/user-attachments/assets/aff55e79-c1f6-4b66-b4f6-441b6c377893" />
3.
<img width="555" height="631" alt="image" src="https://github.com/user-attachments/assets/6ea7200f-5e02-4af3-8cad-ff246c82938d" />

---

### Destinació del backup
A *Backup destination* seleccionem **Google Drive**.

<img width="658" height="590" alt="image" src="https://github.com/user-attachments/assets/4ab44f5e-f715-4e60-a088-6691bc7bfb84" />


---

### Autorització
Haurem d’autoritzar l’accés fent clic al botó indicat i iniciar sessió amb el nostre compte de correu.

- Seleccionem el compte
- Acceptem els termes i condicions

<img width="394" height="335" alt="image" src="https://github.com/user-attachments/assets/4b02f826-bbb3-422c-9e76-bfb0833619bf" />

<img width="274" height="370" alt="image" src="https://github.com/user-attachments/assets/9726a48e-f5d2-4ade-991d-d6d76150bde2" />

<img width="367" height="537" alt="image" src="https://github.com/user-attachments/assets/dcbd7ce8-1f69-4734-8a66-7a400d001ed9" />

---

### Dades d’origen
Seleccionem com a dades d’origen la carpeta:

- `MyDocuments`

<img width="608" height="458" alt="image" src="https://github.com/user-attachments/assets/702f49b6-132e-4b56-b587-a271d25c31f1" />


---

### Planificació
Configurem el backup perquè:
- Es faci **cada dia**
- A les **18:00 hores**

<img width="490" height="560" alt="image" src="https://github.com/user-attachments/assets/20e4bd57-3b3f-4e1a-a780-3851d8cfbffa" />


---

### Opcions finals
Deixem les opcions en **predeterminat**.

Ara ja tindrem:
- Un backup local al disc **D:**
- Un backup al **Google Drive**

<img width="460" height="573" alt="image" src="https://github.com/user-attachments/assets/3a9ccbc4-7ae3-4e37-a6ec-2912b6df0c47" />

<img width="618" height="368" alt="image" src="https://github.com/user-attachments/assets/9218ca33-a5ca-4200-b814-72720c14585d" />

---

## Comprovació del funcionament

1. Esborrem el contingut de la carpeta **Documents**
2. Comprovem el backup local del disc **D:**

<img width="752" height="553" alt="image" src="https://github.com/user-attachments/assets/6838c881-3f32-4186-9d83-c76fd0992ad0" />

---

### Restauració amb Duplicati
Dins de Duplicati:
- Cliquem **Start** a l’apartat **Restores**

<img width="404" height="102" alt="image" src="https://github.com/user-attachments/assets/58a1b9d5-7d3e-4b39-a061-fb7d8466a18a" />

  
- Seleccionem el **primer backup creat**

<img width="646" height="78" alt="image" src="https://github.com/user-attachments/assets/3bb1034d-5281-4473-9bc8-f5e704742b1b" />

  
- Restaurem la carpeta seleccionada

<img width="410" height="25" alt="image" src="https://github.com/user-attachments/assets/d311ba7a-b8a0-4639-a03b-2aedef71d09d" />


I ja tindrem les dades restaurades.

<img width="746" height="416" alt="image" src="https://github.com/user-attachments/assets/2ffecac4-52b9-4669-8a8e-6a0ba7c91fbf" />

---

### Restauració amb Google Drive

- Cliquem **Start**

<img width="738" height="180" alt="image" src="https://github.com/user-attachments/assets/fa6ba28d-3cde-4d56-857c-b2e1f121cb63" />

- Es crea automàticament la carpeta al Drive amb els backups

<img width="743" height="381" alt="image" src="https://github.com/user-attachments/assets/3c85a221-c3d1-4dfd-9f60-0af16c072f86" />


---

## Part 2: Còpia de seguretat servidor Linux

Afegirem un **segon disc de 10 GB** que simularà una unitat auxiliar.

<img width="630" height="489" alt="image" src="https://github.com/user-attachments/assets/d2f7934b-118d-4358-9fd7-1d6b2b49d91d" />


---

### 1. Comprovació del disc
Entrem a la màquina **Linux** i comprovem que detecta el segon disc amb la següent comanda:

```bash
lsblk
```

<img width="503" height="164" alt="image" src="https://github.com/user-attachments/assets/841b6edf-252d-4071-ac67-f87c72812846" />


# Part 2: Còpia seguretat servidor Linux

afegiràs un segon disc de 10 GB que simularà una unitat auxiliar.

<img width="964" height="799" alt="Captura de pantalla 2025-12-16 162916" src="https://github.com/user-attachments/assets/d65be49c-1e03-4f70-b0c4-3b3403ba26d3" />

---

Entrarem al nostre server i comprovarem que veu el segon disc amb aquesta comanda.

```bash
sudo fdisk -l
```
<img width="685" height="435" alt="image" src="https://github.com/user-attachments/assets/84811ee3-67a1-436b-8d02-54123b5d0f16" />

---

Ara crearem una partició nova en el segon disc de 10GB. Posarem primer N (nova partició), P (partició primària), deixarem els valors per defecte i per últim W (per guardar).

```bash
sudo fdisk /dev/sdb
```
<img width="543" height="143" alt="image" src="https://github.com/user-attachments/assets/e0b55a30-a617-4aea-af3a-6dfdb4d5d245" />

<img width="651" height="244" alt="image" src="https://github.com/user-attachments/assets/79410c83-d6b9-4c30-b48f-f87171409d9d" />

---

Comprovem si s'ha creat correctament:

```bash
sudo fdisk -l
```
<img width="684" height="500" alt="image" src="https://github.com/user-attachments/assets/4bd210a9-93e3-42d1-9d1d-976a86eebc00" />

---

Despres de comprovar ficarem el format XFS amb aquesta comanda:

```bash
sudo mkfs.xfs /dev/sdb1
```
<img width="629" height="178" alt="image" src="https://github.com/user-attachments/assets/e5029452-7f0b-4145-93c2-73fafd5a39c2" />

---

Crearem la carpeta /media/backup per despres muntar-la a la carpeta /dev/sdb1:

```bash
sudo mkdir /media/backup
```

```bash
sudo mount /dev/sdb1 /media/backup
```
<img width="370" height="36" alt="image" src="https://github.com/user-attachments/assets/000eda3f-9994-46d3-989f-2b90b733975d" />

---

Ara el següent pas serà instal·lar Duplicity:

```bash
sudo apt install duplicity
```
<img width="305" height="15" alt="image" src="https://github.com/user-attachments/assets/ac72603e-4100-4cfd-b072-eca062e41a04" />

---

Després creem dos usuaris addicionals amb carpetes personals, que seran userjanf i userjanp.

```bash
sudo useradd -m -s /bin/bash userjanf
```
```bash
sudo useradd -m -s /bin/bash userjanp
```
<img width="393" height="35" alt="image" src="https://github.com/user-attachments/assets/084836cf-0775-4c97-91b1-e584f7499e5f" />

---

Per comprovar que s’han creat correctament farem:

```bash
grep -E "userjanf|userjanp" /etc/passwd
```
<img width="406" height="50" alt="image" src="https://github.com/user-attachments/assets/cd6c52dc-3f7e-4189-b284-ae5b3d36550b" />

---

Configurem la contrasenya dels usuaris:

```bash
passwd userijanf
```
```bash
passwd userjanp
```
<img width="317" height="147" alt="image" src="https://github.com/user-attachments/assets/0b143913-b0a4-4f14-bed4-5a666e628068" />

---

Crearem arxius buits sense propòsit només perquè estiguin allà per poder fer la prova a la carpeta home de l’usuari.

```bash
fallocate -l 10MB archivo1
```
<img width="300" height="22" alt="image" src="https://github.com/user-attachments/assets/2f80306e-86d1-4fba-b4aa-85af53afcb76" />

i fem ls per comprovar:

<img width="306" height="80" alt="image" src="https://github.com/user-attachments/assets/dc877319-4d54-412f-a2ae-6d88271217c3" />

---

El següent pas serà fer la còpia de seguretat de la carpeta /home amb la següent comanda:

```bash
sudo duplicity full /home/ file:///media/backup/
```

<img width="557" height="404" alt="image" src="https://github.com/user-attachments/assets/d1d86b2a-007b-4e9c-8d57-db41321d65b5" />


comprovem que s'ha creat correctament:

<img width="1199" height="40" alt="image" src="https://github.com/user-attachments/assets/ab7deeae-0b4f-4d94-ad9c-46b84b8c2964" />

---

Ara esborrarem alguns arxius per poder després fer la restauració:

```bash
rm archivo1 ...
```
<img width="189" height="70" alt="image" src="https://github.com/user-attachments/assets/cc86b14e-10ee-4318-8eea-71661ad7442f" />

I comprovem que ja no els tenim amb:

```bash
ls
```
---

El següent serà fer la restauració del /home de l’usuari, ho farem amb:

```bash
sudo duplicity restore file:///media/backup/ /home/usuari
```
<img width="551" height="69" alt="image" src="https://github.com/user-attachments/assets/cae1e4dd-947d-44e4-825e-43d671f06107" />

---

Després el següent pas serà crear un nou fitxer per fer una altra comprovació.

```bash
fallocate -l 4MB archivo1
```

---

Farem una copia incrementalamb aquesta comanda:

```bash
duplicity full /home/ file:///media/backup
```
<img width="516" height="194" alt="image" src="https://github.com/user-attachments/assets/8790b1eb-f5c2-4be7-b037-4758dc74f0c0" />

---

Ara desmuntarem /media/backup:

```bash
umount /media/backup
```
<img width="259" height="18" alt="image" src="https://github.com/user-attachments/assets/86d48d06-6519-46ff-81f8-ffc625900134" />

---

Ara crearem un script amb bin/bash que farà la còpia completa de /home de l’usuari principal:

<img width="732" height="184" alt="image" src="https://github.com/user-attachments/assets/6c2538d1-a3f7-4e4a-a3d3-9c3316649c60" />

---

Després li donarem permisos d’execució perquè si no no podrem executar-lo.

```bash
chmod +x fullbackup.sh
```
<img width="351" height="18" alt="image" src="https://github.com/user-attachments/assets/b8572717-4307-46ec-b22f-5dca09002f70" />

---

Programem al cron com a root  l’execució de l’script els diumenges a les 23:00.

```bash
sudo crontab -e
```
<img width="253" height="20" alt="image" src="https://github.com/user-attachments/assets/8db9df0b-bfe8-45f9-bfcf-432477633c96" />

<img width="786" height="407" alt="image" src="https://github.com/user-attachments/assets/bbc830f5-1b32-42ac-abb0-132346628b9a" />

---

creem un altre arxiu executable de bin/bash, que sigui l’incremental.

```bash
sudo nano incrementalbackup.sh
```

<img width="764" height="186" alt="image" src="https://github.com/user-attachments/assets/ba849c9f-bb8f-4092-a2fc-08ae8e49a568" />

---

Donarem també els permisos amb chmod.

```bash
sudo chmod +x incrementalbackup.sh
```
<img width="411" height="19" alt="image" src="https://github.com/user-attachments/assets/2e41042e-3972-4397-afbe-c6ca020a1f29" />

Comprovem que s'han creat correctament amb la comanda:

```bash
ls -l
```

<img width="493" height="64" alt="image" src="https://github.com/user-attachments/assets/1f0e8af8-9eb7-4d7e-ba13-f1c5f806c309" />

---

Executem el programa cron per configurar que es repeteixi a les 23 hores:

```bash
sudo crontab -e
```

<img width="788" height="434" alt="image" src="https://github.com/user-attachments/assets/660b89b1-f49b-4074-9365-03ce861f2418" />

