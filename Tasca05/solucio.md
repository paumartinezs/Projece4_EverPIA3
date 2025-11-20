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


