
## Part 2: Còpia seguretat servidor Linux

### En primer lloc instal·la la maquina virtual de Ubuntu server

### Selecciona el teu idioma 

<img width="1257" height="785" alt="image" src="https://github.com/user-attachments/assets/f5d84886-b6b7-42ea-b5c4-658fd4f2348b" />

### Prem "Hecho"

<img width="1065" height="834" alt="image" src="https://github.com/user-attachments/assets/7ad0f2be-ee0e-46d8-a62e-f9ca1685892f" />

<img width="1062" height="814" alt="image" src="https://github.com/user-attachments/assets/8669798c-85c1-42f5-9560-8dfca6695ea9" />

<img width="1070" height="826" alt="image" src="https://github.com/user-attachments/assets/c63ec640-afd6-4840-9e3e-2c8a7d32bdb7" />

<img width="1063" height="803" alt="image" src="https://github.com/user-attachments/assets/caff5ae8-7d62-45a2-b007-255a64942fa7" />

<img width="1275" height="795" alt="image" src="https://github.com/user-attachments/assets/3d93c87e-efee-48de-8b73-678cb544dee1" />

<img width="1267" height="789" alt="image" src="https://github.com/user-attachments/assets/a0f68243-b905-4d7b-ba11-b9db57cc1939" />

### Prem continuar

<img width="577" height="202" alt="image" src="https://github.com/user-attachments/assets/dfaacb99-ca8e-473c-9e48-c43e38519ee1" />

### Afegim nom de la maquina i una contrasenya

<img width="1273" height="790" alt="image" src="https://github.com/user-attachments/assets/0bcba3cd-8734-4ad5-8e80-8fecd102caa0" />

### Prem reiniciar ahora 

<img width="1197" height="789" alt="image" src="https://github.com/user-attachments/assets/1dfea134-c3f7-40dc-a0ea-6fc02fddb1af" />

### Un cop iniciada la maquina, utilitza aquesta comanda per comprovar que surt el disc que has creat

``` bash
sudo fdisk -l
```
<img width="823" height="544" alt="image" src="https://github.com/user-attachments/assets/f7f0331a-54cd-4265-a90c-3c391a5d0c5e" />

## 1. Inicialitza i formata en format xfs.

### Crea una partició

``` bash
sudo fdisk /dev/sdb
```
<img width="770" height="500" alt="image" src="https://github.com/user-attachments/assets/2b784087-51a7-49ee-82f8-ced12573da14" />

### Com surt marcada a la captura de pantalla

N = Per Crear nova partició
P = Primari
Prem enter = Per tenir els valors per defecte
W = Per guardar

### Comprova que s'ha crat de manera correcta amb la mateixa comanda del principi

<img width="806" height="632" alt="image" src="https://github.com/user-attachments/assets/dcf47602-eafa-40bd-95c5-e319837635df" />

### Un cop creada la partició, donal·li el format XFS amb la seguetn comanda

``` bash
sudo mkfs.xfs /dev/sdb1
```
<img width="718" height="241" alt="image" src="https://github.com/user-attachments/assets/9bbbcf90-1d28-4e77-9995-cf8111a90940" />

### Crea la carpeta

``` bash
sudo mkdir -p /media/backup
```
<img width="388" height="52" alt="image" src="https://github.com/user-attachments/assets/9c4daeeb-2b37-488d-8e98-5973d393ba26" />

### Fes el muntatge manualment mab aquesta comanda

``` bash
Sudo mount /dev/sdb1 /media/backup
```
<img width="473" height="42" alt="image" src="https://github.com/user-attachments/assets/a1c0e843-35f4-48e8-908e-f5b15ec10364" />

## 2. Instal·lació duplicity.

### Instal·la duplicity

``` bash
sudo apt install duplicity
```
### Prem s

<img width="843" height="294" alt="image" src="https://github.com/user-attachments/assets/2f46ae5a-b55d-4185-80e6-a11d03ae7572" />

<img width="946" height="980" alt="image" src="https://github.com/user-attachments/assets/4996c673-4885-470c-81f5-63c89f2af754" />

### Comprova que s'ha instal·lat de manera correcta

``` bash
duplicity --version
```
<img width="396" height="69" alt="image" src="https://github.com/user-attachments/assets/b5185ea7-80be-4780-a30c-70107bada335" />

### Crea dos usuaris que tinguin carpeta personal

``` bash
sudo useradd -m -s /bin/bash usuari2
sudo useradd -m -s /bin/bash usuari3
```
<img width="472" height="65" alt="image" src="https://github.com/user-attachments/assets/6ecc14e7-6af9-4fdd-9267-a1031df44066" />

### Comprova que has creat els dos usuaris correctament amb la comanda grep

``` bash
grep -E "usuari2|usuari3" /etc/passwd
```
<img width="502" height="84" alt="image" src="https://github.com/user-attachments/assets/73ffd21c-be49-4de6-b736-678abdb9a73a" />

### Afageix·li contrasenyes als dos usuaris

``` bash
sudo passwd usuari2
sudo passwd usuari3
```
<img width="468" height="178" alt="image" src="https://github.com/user-attachments/assets/82f8879b-6dbf-4ea0-8244-d8242c13f148" />

### Crea 4 arxius per prova de la copia de seguretat 

``` bash
 fallocate -l 10MB arx1
 fallocate -l 10MB arx2
 fallocate -l 10MB arx3
 fallocate -l 10MB arx4
```
### I "ls" per comprovar que s'han creat correctament

<img width="360" height="144" alt="image" src="https://github.com/user-attachments/assets/102c16da-5872-44ba-9008-d09dab9e685c" />

### Fes una copia de seguratet a tota la carpeta /home

``` bash
sudo duplicity full /home/ file:///media/backup/
```

### Afageixl·li contrasenya per desencriptar en el meu cas usuari

<img width="706" height="466" alt="image" src="https://github.com/user-attachments/assets/bc836099-5d39-4780-b851-26623aa15c35" />

### Comprova que s'ha creat la copia de seguretat correctament en el disc secundari utilitzant ls dintre de /media/backup

<img width="590" height="98" alt="image" src="https://github.com/user-attachments/assets/1f824e42-21ea-46bf-b2ff-04f585b77b21" />

### Elimiina els Arxius de prova

``` bash
rm arx*
```

<img width="217" height="49" alt="image" src="https://github.com/user-attachments/assets/f73752e4-a06f-4dbb-8d8a-9a2b1ec28480" />

### Ara fes la restauració de la copia de seguretat per recuperar els arxius eliminats anteriorment

``` bash
sudo duplicity restore file:///media/backup/ /home/usuari
```
### Abans de fer la comanda entra a la carpeta /media/backup amb cd

``` bash
cd /media/backup
```
<img width="775" height="97" alt="image" src="https://github.com/user-attachments/assets/a8e23eb0-e32f-4a90-8524-f774e7ba3e0a" />

### Comprova que s'han resturat correctament amb ls dintre del usuari en el meu cas "pau

<img width="221" height="38" alt="image" src="https://github.com/user-attachments/assets/638c464e-27ad-4aa2-8abe-57ab79c1e1bf" />

### Crea un altre arxiu de 4 MB

``` bash
fallocate -l 4MB arx5
```
<img width="423" height="86" alt="image" src="https://github.com/user-attachments/assets/ac15417a-662d-4574-835e-bce076084fe3" />

### Fes una nova còpia de seguretat

``` bash
sudo duplicity /home/ file:///media/backup/
```
<img width="950" height="527" alt="image" src="https://github.com/user-attachments/assets/996ce476-c661-414e-884e-338ff0ae08d1" />

### Desmunta la unitat del backup

``` bash
sudo umount /media/backup
```

<img width="448" height="52" alt="image" src="https://github.com/user-attachments/assets/b6dc190a-20cb-4260-b1db-f06ca364e19d" />

### 
