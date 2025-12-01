# T05: Accés Remot

### Abans de iniciar la maquina de linux, afegeix una segona interficie en "Host only"

<img width="860" height="493" alt="image" src="https://github.com/user-attachments/assets/dd6d8e73-7a34-41b2-8931-ad14185c9507" />


### En primer lloc instal·la el ssh.

``` bash
sudo apt install ssh
```

<img width="878" height="552" alt="image" src="https://github.com/user-attachments/assets/4fc96ca9-70c0-4a50-8227-a1da73de1418" />

### Cambia la configuració de la segona interficie perque et doni una IP automatica.

<img width="814" height="191" alt="image" src="https://github.com/user-attachments/assets/c7416144-b3a1-422b-a90e-25c86c9440b1" />

### Guardem la configuració del netplan

``` bash
sudo netplan apply
```

### Per comprovar les IPs en linux pots utilitzar aquestes comandes

``` bash
ip addr show
```
o

``` bash
ip a
```
<img width="911" height="360" alt="image" src="https://github.com/user-attachments/assets/a24a91bd-1f03-47e8-a328-68833d7d08db" />

### En la maquina virtual de windows, comprova la connexió entre les dos maquines amb aquesta comanda

``` bash
ssh usuari@IP

```
<img width="693" height="579" alt="image" src="https://github.com/user-attachments/assets/ac8c4301-a259-4a75-ad1b-f3de10986ec1" />

### Comprova que es treballa igual que en la maquina de ubunut server

``` bash
hostname
```

<img width="670" height="507" alt="image" src="https://github.com/user-attachments/assets/ed9bdc30-aad3-463c-a498-61178c0564c9" />

### Abans de entrar a l'arxiu de condiguració, habilita l'usuari root al ubuntu i fica una nova contrasenya.

``` bash
Sudo passwd root
```

<img width="346" height="130" alt="image" src="https://github.com/user-attachments/assets/17abecdc-5335-4038-8b41-0f9b38de1528" />

### Ara entra a l'arxiu de configuració

``` bash
Sudo nano /etc/ssh/sshd_config

```
<img width="953" height="798" alt="image" src="https://github.com/user-attachments/assets/c27c3f27-5a6b-406c-b766-cc8b08609e81" />


### Afegeix aixo a l'arxiu de configuració

``` bash
AllowUsers "usuari"
```
<img width="1042" height="762" alt="image" src="https://github.com/user-attachments/assets/b7136124-04a8-45c5-a450-331de89516bd" />


### Ara fes un login en local amb el usuari root

``` bash
su - root
```

<img width="236" height="64" alt="image" src="https://github.com/user-attachments/assets/18549531-4761-4f80-8bb3-2d63ad4ca10d" />

### Ves a la maquina virtual de windows i fes un ssh root.

<img width="572" height="274" alt="image" src="https://github.com/user-attachments/assets/7ce5bc35-4aac-4311-bead-5cdfbb900bf8" />

### Ara genera codis RSA  amb aquesta comanda

``` bash
ssh-keygen -t rsa
```

<img width="730" height="517" alt="image" src="https://github.com/user-attachments/assets/7cf16126-6b99-4420-a592-a5ea9270a3ad" />

### Mira si tens els arxius que es necessiten

### Abans de mirar els larxius, entra al teu usuari utilitzant cd:

``` bash
cd Users\pau
```

``` bash
ls .\.ssh\
```
<img width="642" height="294" alt="image" src="https://github.com/user-attachments/assets/22886193-8363-4b4d-bf22-d17b7706f95b" />

### Ara copia el .pub de la Maquina virtual de ubuntu i copiala al Windows utilitzant aquesta comanda

``` bash
scp.\.ssh\id_rsa.pub usuari@IP:/home/usuari
```
<img width="958" height="132" alt="image" src="https://github.com/user-attachments/assets/3bc07478-72fd-4589-b4c8-9f207d7b5559" />

<img width="790" height="299" alt="image" src="https://github.com/user-attachments/assets/01fc5955-88b1-4e20-950e-2356ed075a40" />

### Torna a la mauqina virtual de ubuntu per crear un arxiu a la carpeta ssh

``` bash
Touch .ssh/authorized_keys
```

<img width="361" height="56" alt="image" src="https://github.com/user-attachments/assets/228a22b7-9165-4564-a225-330bcffd1658" />

### Ara copia la clau id_rsa.pub dins del arxiu creat

``` bash
Cat id_rsa.pub >> .ssh/authorized_keys
```
<img width="429" height="50" alt="image" src="https://github.com/user-attachments/assets/350d7b39-6a7c-4515-873f-9bb2f5984652" />

### Torna a la maquina virtual de Windows i fes un ssh

<img width="753" height="643" alt="image" src="https://github.com/user-attachments/assets/d7ee9de2-06d8-4d4d-9947-7efa0b6912fe" />

### Ara ves a l'apartat de "Sistema - Características opcionales - Ver características"

<img width="796" height="627" alt="image" src="https://github.com/user-attachments/assets/1cda96f4-4af2-43a3-a9b4-19d9b01e62e5" />

<img width="799" height="625" alt="image" src="https://github.com/user-attachments/assets/6e27b49e-867a-4009-a6c0-ed6ca68c6752" />

<img width="796" height="628" alt="image" src="https://github.com/user-attachments/assets/ed0abf23-2df1-4fd8-94e4-f6d4999e7138" />

<img width="452" height="372" alt="image" src="https://github.com/user-attachments/assets/b78c475f-d5bb-4b97-be6d-42171d0c45d9" />

<img width="731" height="677" alt="image" src="https://github.com/user-attachments/assets/a58062df-a087-4914-93ad-b70a3c872392" />

### Busca OpenSSH i prem "afegir"

<img width="541" height="628" alt="image" src="https://github.com/user-attachments/assets/afebcb63-a467-4029-8589-320dedb5d7a1" />

### Ara apaga el firewall a dins de "Seguridad de windows - Firewall i protección de red" 

<img width="801" height="631" alt="image" src="https://github.com/user-attachments/assets/86c94756-69dd-4e1c-9c25-3ce0767cd28d" />

<img width="797" height="626" alt="image" src="https://github.com/user-attachments/assets/170c7b77-6419-46d3-a825-81c77b1e15c5" />

<img width="798" height="625" alt="image" src="https://github.com/user-attachments/assets/46c572a6-f2ed-4a71-abe3-03f844dd1302" />

### Ara entra a powershell per amb administrador i activa el ssh

<img width="770" height="662" alt="image" src="https://github.com/user-attachments/assets/a6aead29-1103-4bb5-a2d1-7400297f1bcf" />
<img width="352" height="71" alt="image" src="https://github.com/user-attachments/assets/e466a91c-50d8-4a9b-be49-6f48b97b6916" />


### Ara fes que cada cop que inicies la maquina, tambue s'encéngui el servei

``` bash
Set-Service -Name sshd -StartupType "Automatic"
```
<img width="548" height="60" alt="image" src="https://github.com/user-attachments/assets/1abb8b68-5c27-4efa-8db2-c04957fd63c1" />

### Fes un "Ipconfig" per veure que te la interficie de hostonly que l'utilitzaras per conectar-te en la maquina virtual de Ubuntu

``` bash
ipconfig
```

<img width="870" height="556" alt="image" src="https://github.com/user-attachments/assets/b8cd1f8b-2d1a-4f5e-9b63-eabe67f7d854" />

### Ara fes un ping amb la ip del hostonly de la maquina de windows per veure si les màquines es poden comunicar

``` bash
ping "IP"

```

<img width="507" height="132" alt="image" src="https://github.com/user-attachments/assets/14ed1164-0b66-4bfd-9031-aa8720ffb760" />

### Ara conectat a la maquina virtual de Windows desde el ubuntu

``` bash
ssh usuari@IP del hostonly de windwos
```

<img width="528" height="105" alt="image" src="https://github.com/user-attachments/assets/15cb5387-dbc2-4e2d-9ff8-40e3d4a924cc" />

## Creació d'un Túnel

### Torna a powershell de windows per començara crear el túnel

``` bash
Ssh -D 9876 usuari@192.168.56.102
```
<img width="639" height="542" alt="image" src="https://github.com/user-attachments/assets/03ebcf5f-d25c-4189-a6b3-adf9c5e04bc6" />

### Ara configura el túnel amb proxy, entra a  "Panel de control - Redes e Internet"

<img width="776" height="590" alt="image" src="https://github.com/user-attachments/assets/c8ad5380-2f1d-4c1f-8726-0c77e4bdc763" />

<img width="778" height="593" alt="image" src="https://github.com/user-attachments/assets/0fe28cec-1496-4552-810c-51db06530002" />

### Entra a "Conexiones - Configuración de LAN"

<img width="375" height="336" alt="image" src="https://github.com/user-attachments/assets/c75a93dd-c70c-4b51-9f60-aa807bb06562" />
