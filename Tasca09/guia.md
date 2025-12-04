# Guia servidors fitxers linux

Abans de iniciar la maquina, afageix una segona interficie a les dues maquines de host-only per la comunicació entre elles

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

### Ara crea els grups i els usuaris desde el client
