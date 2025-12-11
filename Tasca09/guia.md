# Guia servidors fitxers linux

Abans de iniciar la maquina, afageix una segona interficie a les dues maquines de host-only per la comunicació entre elles

# Fase 2: Preparació del servidor

### En primer lloc utiltiza aquesta comanda per actualitzar els paquets

``` bash
sudo apt upgrade && sudo apt update
```
### En primer lloc despres de crear les dues maquines, crea dos grups: devs i admins en les dues maquines

``` bash
sudo groupadd devs && sudo groupadd admins
```

<img width="495" height="69" alt="image" src="https://github.com/user-attachments/assets/2d6723e5-cbdf-4f3b-8bff-affbbc23714c" />

<img width="542" height="100" alt="image" src="https://github.com/user-attachments/assets/efdd2fa3-2196-466f-96ae-dc82cc591925" />

### A continuació crea dos usuaris:

### Un que es digui dev01 que formi part del grup devs

``` bash
sudo useradd -G devs -m -s /bin/bash dev01
```

<img width="491" height="63" alt="image" src="https://github.com/user-attachments/assets/1bf07503-c9a3-421e-893e-4f9574fdaa27" />

<img width="545" height="69" alt="image" src="https://github.com/user-attachments/assets/38d84035-e3f7-4ff6-83ed-2c183a84428a" />

### Crea un altre que es digui admin01 i que formi part de admins

``` bash
sudo useradd -G admins -m -s /bin/bash admin01
```
<img width="534" height="56" alt="image" src="https://github.com/user-attachments/assets/459f2518-a330-4b00-84c6-0fb8da1445f9" />

<img width="565" height="70" alt="image" src="https://github.com/user-attachments/assets/48b16f5e-e43c-4f1d-8b98-4a4134bb948c" />

### Crea el directori per als projectes de desenvolupament en la ruta /srv/nfs/dev_projects

``` bash
sudo mkdir /srv/nfs/dev_projects
```
<img width="422" height="73" alt="image" src="https://github.com/user-attachments/assets/cfad5d95-34ff-43c2-bf9b-dea81efdc4b3" />

### Crea un directori per a les eines d'administració

``` bash
sudo mkdir /srv/nfs/admin_tools
```
<img width="392" height="46" alt="image" src="https://github.com/user-attachments/assets/7ecdd0a8-3b6d-4c30-b51c-bfffe91bd255" />

### Ara canvia els permisos de les carpetes amb el chown

### Per canviar la propietat de la carpeta

``` bash
sudo chown root:devs /srv/nfs/dev_projects

sudo chown root:admins /srv/nfs/admin_tools
```
<img width="505" height="56" alt="image" src="https://github.com/user-attachments/assets/224bafde-3959-4d1a-8ed2-5aee44bf48a3" />

<img width="488" height="46" alt="image" src="https://github.com/user-attachments/assets/0b69fba5-619c-4a09-a696-74751d299889" />

### Asigna els permisos a les carpetes

``` bash
sudo chmod 770 /srv/nfs/dev_projects
```
<img width="460" height="67" alt="image" src="https://github.com/user-attachments/assets/b28d2094-e687-42e3-93ec-0f34c2515ccc" />

``` bash
sudo chmod 770 /srv/nfs/admin_tools
```
<img width="439" height="54" alt="image" src="https://github.com/user-attachments/assets/0e8065f9-6d98-44a0-bd05-8cd4751557f4" />

### Instal·la el servidor de NFS amb aquesta comanda 

``` bash
sudo apt install nfs-kernel-server
```
<img width="657" height="257" alt="image" src="https://github.com/user-attachments/assets/72a7b32b-e8b4-4766-88c6-9b6354c9d8da" />

<img width="959" height="797" alt="image" src="https://github.com/user-attachments/assets/d84a6d9c-bad4-4749-bfb0-c81ab190d7bd" />

### Comprova el estat del nfs utilitzant aquesta comanda

``` bash
systemctl status nfs-kernel-server
```

<img width="800" height="254" alt="image" src="https://github.com/user-attachments/assets/8ff820bc-f983-4068-b60f-c6b999e738a4" />


### Obra l'arxiu de /etc/exports

``` bash
sudo nano /etc/exports

```

### I introdueix aquesta linia abaix de tot

``` bash
/srv/nfs *(rw,sync,no_subtree_check)
```

<img width="790" height="277" alt="image" src="https://github.com/user-attachments/assets/53669a06-ca31-4c95-9073-e2e05cacf37b" />

### Aplica els canvis reinciant el servei

``` bash
systemctl restart nfs-kernel-server
```

<img width="584" height="133" alt="image" src="https://github.com/user-attachments/assets/475e8fbd-a2cf-4354-a9ef-3086f1b33623" />

### Utilitza aquesta comanda per veure els arxius que es poden exportar

``` bash
exportfs -u
```

<img width="385" height="49" alt="image" src="https://github.com/user-attachments/assets/51da6513-cf68-48c5-942a-6629b082dc55" />

### Pots veure des de quin port treballa utilitzant aquesta comanda

``` bash
rpcinfo -p 192.168.56.114
```

<img width="411" height="505" alt="image" src="https://github.com/user-attachments/assets/81090af9-a9f5-453a-ae0e-19e5e7c8be9b" />


### Conectat al servidor utilitzant aquesta comanda

``` bash
showmount -e 192.168.56.114
```

<img width="426" height="55" alt="image" src="https://github.com/user-attachments/assets/566c4d26-8a1a-403e-8ab0-611a8a46d8f6" />

# Fase 3: L'Exportació d'Administració (El Dilema del root_squash)

### Crea la carpeta /mnt/admin_tools

<img width="471" height="40" alt="image" src="https://github.com/user-attachments/assets/89b7a392-7932-47a9-b768-bdcf2569b480" />

### Una vegada creada la carpeta, munta el recurs utilitzant la mount amb aquesta comanda

``` bash
mount -t nfs 192.168.56.114:/srv/nfs/admin_tools /mnt/admin_tools
```
<img width="645" height="92" alt="image" src="https://github.com/user-attachments/assets/7576a61c-396d-47e6-b2e0-1485b8015cb7" />

<img width="543" height="35" alt="image" src="https://github.com/user-attachments/assets/837a96eb-d843-47f2-8707-fd4df0fa4ddb" />

# Prova 2 (solució)

### Edita l'arxiu de /etc/exports i afageix aquestes dues lines:

``` bash

/srv/nfs/admin_tools *(rw,sync,no_subtree_check,no_root_squash)
/srv/nfs/dev_projects *(rw,sync,no_subtree_check)
```

<img width="954" height="1030" alt="image" src="https://github.com/user-attachments/assets/07ebb456-efd2-45ac-95f2-08703c93b183" />

### Reincia el servei per guardar els canvis

``` bash
systemctl restart nfs-kernel-server
```

<img width="626" height="197" alt="image" src="https://github.com/user-attachments/assets/01a72f3c-1f79-49ec-a296-fe160d239435" />

### Desmonta i torna a muntar el recurs amb aquestes comandes:

### Per desmontar

``` bash
umount -t nfs 192.168.56.114:/srv/nfs/admin_tools /mnt/admin_tools
```

<img width="643" height="165" alt="image" src="https://github.com/user-attachments/assets/a01ae12c-6ef4-4973-a99e-8707174213b4" />

### Per muntar

``` bash
mount -t nfs 192.168.56.101:/srv/nfs/admin_tools /mnt/admin_tools
```
<img width="640" height="112" alt="image" src="https://github.com/user-attachments/assets/c35c1a19-2822-41c2-af2a-e5bddb5f648e" />

### Ara crea un nou arxiu anomenat "File2"

<img width="533" height="50" alt="image" src="https://github.com/user-attachments/assets/c5cc8cfa-6e1a-4a5b-a9e8-22e2dff384bf" />

<img width="877" height="486" alt="image" src="https://github.com/user-attachments/assets/ccc2d3d7-c1e3-4368-b816-e81bb1cb3a3b" />

# Fase 4: L'Exportació de Desenvolupament

### Modifica una altre vegada l'arxiu /etc/exports, borra la linia de "/srv/nfs/dev_pjects" i afegeix aquestes dues:

``` bash
/srv/nfs/dev_projects 192.168.56.0/24(rw,sync,no_subtree_check)
/srv/nfs/dev_projects 192.168.56.140(ro,sync,no_subtree_check)
```
<img width="954" height="1027" alt="image" src="https://github.com/user-attachments/assets/9a42f7b2-ebbb-4478-b6c5-03a3087c4348" />


