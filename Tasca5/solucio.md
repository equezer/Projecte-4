# Guia T05: Accés Remot. Connexió via SSH

<img width="747" height="419" alt="image" src="https://github.com/user-attachments/assets/35d8f523-4e76-47e7-9097-b01050544c2e" />

### Jan Fernández Paulinelli

### Serveis de Xarxa

20/11/2025
---

## Activitas a fer: 


## 1. Utilitzarem dues maquines, una amb Zorin i l'altre amb Windows11 amb dues interficies de xarxa de les quals serien (NAT i Adaptador de només l'anfitrio)

<img width="614" height="303" alt="image" src="https://github.com/user-attachments/assets/0998c0a4-1639-4940-b596-4830fef5c5bb" />

<img width="612" height="303" alt="image" src="https://github.com/user-attachments/assets/8a17b096-3ff4-4cb2-a096-16c774b17956" />

## 2. Instal·larem el servei SSH primer a Zorin amb aquesta comanda:

```bash
sudo apt install ssh
```
<img width="625" height="321" alt="image" src="https://github.com/user-attachments/assets/c2e8d117-76b8-474e-8490-9b48801e3bd4" />   

## 3. comprovarem la ip de la nostra màquina Zorin de Linux:

```bash
ip a
```
<img width="635" height="413" alt="image" src="https://github.com/user-attachments/assets/e2183283-bf34-45f6-98a5-6cba9e20248c" />

## 4. Anem a la nostra maquina Windows i ens connectarem amb SSH amb l'usuari de Zorin (osigui el nom i la ip) on ens demanarà confirmar posant "yes"

```bash
ssh jan@192.168.56.102
```    
<img width="658" height="142" alt="Captura de pantalla 2025-12-01 172117" src="https://github.com/user-attachments/assets/249eaa11-1f58-490a-aee8-45cd8e74d786" />

## 5. Habilitarem l'usuari root posant-li una contrasenya nova que en meu cas seria "Jancito_10"

```bash
sudo passwd root
```

<img width="333" height="54" alt="image" src="https://github.com/user-attachments/assets/051929ca-e874-4619-b131-bb53e75f09cd" />
  
## 6. Entrem L'arxiu de configuració que entrariem amb aquesta comanda: 

```bash
sudo nano /etc/ssh/sshd config
```
<img width="740" height="637" alt="image" src="https://github.com/user-attachments/assets/f80951e9-46ed-4cdd-8fcb-6feb0737d600" />

## 7. Després farem login localment amb l’usuari root

```bash
su - root
```

<img width="269" height="52" alt="image" src="https://github.com/user-attachments/assets/c67864ff-87e3-4c2f-96e4-5cf7ab5ede6e" />

## 8. Intentarem fer SSH des de la nostra màquina Windows amb l’usuari root i veurem que ens retorna access denied.

```bash
ssh root@192.168.56.102
```

<img width="387" height="32" alt="image" src="https://github.com/user-attachments/assets/5d8305a8-8463-45b2-a065-fd4cc930a4f4" />

## 9. Seguint a la màquina Windows generarem dues claus RSA.

```bash
ssh root@192.168.56.102
```

<img width="569" height="343" alt="image" src="https://github.com/user-attachments/assets/e4555ade-1c62-4ad3-9813-2e49425693e8" />

## 10. Ara desde l'usuari de Windows farem un ls i buscarem un arxiu que acabi en .pub

```bash
ls .\.ssh\
```

<img width="539" height="204" alt="Captura de pantalla 2025-12-01 184611" src="https://github.com/user-attachments/assets/9fc3ff78-0bf2-4f1f-a40f-679ae00b5f28" />

## 11. Copiarem l'arxiu amb la comanda scp

```bash
scp .\.ssh\id_rsa.pub jan@192.168.56.102:/home/jan
```

<img width="965" height="85" alt="image" src="https://github.com/user-attachments/assets/6ea9d67b-2d92-4bec-8c13-7cf1763fcbaa" />


## 12. Crearem al nostre servidor Linux el següent arxiu dins la carpeta .ssh

```bash
touch .ssh/authorized_keys 
```

<img width="387" height="18" alt="image" src="https://github.com/user-attachments/assets/395e45b2-f721-4c65-98a2-a0e9bdfb7a41" />

## 13. copiem l'arxiu a la clau id_rsa.pub

```bash
cat id_rsa.pub >> .ssh/authorized_keys
```

<img width="483" height="22" alt="image" src="https://github.com/user-attachments/assets/a8bb2199-1ff3-43f9-b0c3-77cd443d8f9f" />

## 14. comprovem que podem entrar a SSH sense requerir de contrasenya amb aquesta comanda:

```bash
ssh jan@192.168.56.102
```

<img width="512" height="218" alt="Captura de pantalla 2025-12-01 191417" src="https://github.com/user-attachments/assets/4c0727f5-6fd3-4fd2-a742-af3afd69c938" />

## 15. habilitem el servidor OpenSSH, que per defecte està desactivat en Windows 11:

anirem a Sistema>>Caracteristicas opcionales>>ver características>>Características disponibles

i busquem "Servidor OpenSSH".

<img width="807" height="630" alt="image" src="https://github.com/user-attachments/assets/f5e7e2ee-b1a0-47fd-a751-dec12697d378" />

<img width="799" height="629" alt="image" src="https://github.com/user-attachments/assets/b7accb47-aa88-4d43-96b0-154d160c4817" />

<img width="552" height="630" alt="image" src="https://github.com/user-attachments/assets/a9631e1d-e04f-41d6-b51f-e51478c8c9ed" />

<img width="552" height="635" alt="image" src="https://github.com/user-attachments/assets/20f2dd74-b954-4b7a-acab-dbc98afc3313" />

## 16. Encenem el servei SSH amb Powershell com administrador i indiquem que el servei arranqui automàticament

```bash
Start-Service sshd
```
```bash
Set-Service -Name sshd -StartupType 'Automatic'
```

<img width="581" height="37" alt="image" src="https://github.com/user-attachments/assets/65038c84-4ef7-439e-93bb-bf5b1f5382ac" />

## 17. Si fem una connexió SSh podrem conectar de Windows a Linux 

per aixo primer desconnectarem el firewall de Windows

<img width="779" height="591" alt="image" src="https://github.com/user-attachments/assets/c76fd79d-784c-4c6f-943e-3ff951abdc3b" />

i ara desde Zorin comprovem l'usuari amb aquestes comandes:

<img width="637" height="91" alt="image" src="https://github.com/user-attachments/assets/fd85145f-4be4-4367-906f-f99c6edc40d4" />


<img width="862" height="147" alt="image" src="https://github.com/user-attachments/assets/3d6bee9f-b037-4315-aa46-28bbe9b6bb26" />

creem un socks dinàmic:

<img width="488" height="210" alt="image" src="https://github.com/user-attachments/assets/257d1687-e0c6-4505-bca9-c05b555dfd31" />

## 18. Entrarem a Opcions d’Internet i seguirem els passos per crear el túnel SSH:

<img width="423" height="583" alt="image" src="https://github.com/user-attachments/assets/076c529c-3fed-4b96-8a06-490b763c1a02" />

<img width="432" height="576" alt="image" src="https://github.com/user-attachments/assets/b7ae4c6c-f8a6-415f-9a2b-c07fa5ccc504" />

<img width="379" height="336" alt="image" src="https://github.com/user-attachments/assets/8f0b05bc-8509-436a-b965-4d644e7a39a4" />

<img width="426" height="500" alt="image" src="https://github.com/user-attachments/assets/8ae13b08-825b-4e0b-9487-1966557dcf13" />

## 19. Ara a Wireshark entrem a l'opció de ethernet 2 y veurem l'informació encriptada

com exemple entrarem a youtube: i el desarem obert

<img width="881" height="671" alt="image" src="https://github.com/user-attachments/assets/2dbae776-f5d5-49c4-b17d-1e59b309589b" />


