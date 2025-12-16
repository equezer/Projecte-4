

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
