
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


