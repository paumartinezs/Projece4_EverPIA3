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
AllowUsers usuari
```
<img width="915" height="801" alt="image" src="https://github.com/user-attachments/assets/464c0364-2f20-44e0-96d6-f6d7b88c0a57" />

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

``` bash
ls .\.ssh\
```
<img width="642" height="294" alt="image" src="https://github.com/user-attachments/assets/22886193-8363-4b4d-bf22-d17b7706f95b" />

