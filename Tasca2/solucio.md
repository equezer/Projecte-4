

# Part 2: Còpia seguretat servidor Linux

afegiràs un segon disc de 10 GB que simularà una unitat auxiliar.

<img width="964" height="799" alt="Captura de pantalla 2025-12-16 162916" src="https://github.com/user-attachments/assets/d65be49c-1e03-4f70-b0c4-3b3403ba26d3" />

---

Entrarem al nostre server i comprovarem que veu el segon disc amb aquesta comanda.

```bash
sudo fdisk -l
```
<img width="685" height="290" alt="image" src="https://github.com/user-attachments/assets/0771305f-2c23-4d20-99c0-6c66ec3fd349" />

---

Ara crearem una partició nova en el segon disc de 10GB. Posarem primer N (nova partició), P (partició primària), deixarem els valors per defecte i per últim W (per guardar).

```bash
sudo fdisk /dev/sdb
```

