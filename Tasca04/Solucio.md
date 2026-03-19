# 1. Monitorització de Recursos
- El client vol assegurar-se que el nou servidor dimensionat suporta la càrrega de treball.
- Accediu al Monitor de Rendiment o al Gestor de Tasques del servidor i Realitzeu una captura on es vegi clarament l'estat actual de la CPU i la Memòria RAM disponible.

<img width="805" height="641" alt="image" src="https://github.com/user-attachments/assets/3fa214d1-3629-4df3-b3d5-81c791164061" />

<img width="784" height="613" alt="image" src="https://github.com/user-attachments/assets/d20a96cc-1ad3-4587-b93b-a16e9c3f1d9c" />

<img width="797" height="621" alt="image" src="https://github.com/user-attachments/assets/d88b2ff9-5aec-4ac6-9a73-64795b40f6ef" />

## Interpreteu breument les dades: El servidor està saturat o treballa sense estrès?
El servidor està treballant de forma normal. Com podem veure a les imatges, la CPU al encendre la màquina anava més cargada, però es normal, després la CPU i la memoria RAM rendeixen correctament.

# 2. Configuració d'Auditoria de Seguretat
## Per detectar possibles atacs de força bruta (intents d'endevinar contrasenyes), heu d'activar el registre d'accessos.
Haurem de buscar per el **Group Policy Management Editor** fins arribar **Audit Policy** i activar el **Audit object acces**.

<img width="802" height="595" alt="image" src="https://github.com/user-attachments/assets/9f6c98e3-e12c-4ddf-bd09-350bbbad634a" />

---
Elegire la auditoria de **Audit account logon events** perquè aixi em pot dir a més dels logins, els comptes que han intentat entrar.
## Configureu la política d'auditoria (via GPO o política local del servidor) per auditar els successos d'inici de sessió. És imprescindible que activeu tant els èxits (per saber qui entra) com els fracassos (per saber qui intenta entrar sense permís).
Activarem la auditoria de la imatge.

<img width="437" height="557" alt="image" src="https://github.com/user-attachments/assets/13ebdeff-5652-4b16-aaf8-9954d617a297" />


# 3. Simulació d'Incidents (Hacking Ètic)
## Ara posareu a prova el sistema que acabeu de configurar.

1. Tanqueu la sessió actual.

<img width="488" height="373" alt="image" src="https://github.com/user-attachments/assets/6ebed21b-1f64-49a1-8ef2-de65151e1da8" />

---
2. Intenteu iniciar sessió amb un usuari existent (ex: un usuari de magatzem) però introduint la contrasenya incorrecta expressament. Repetiu aquest procés 3 o 4 vegades seguides.

<img width="1021" height="760" alt="image" src="https://github.com/user-attachments/assets/564804b3-91ce-4087-b699-18e1f2ae4ab5" />

---
3. Finalment, inicieu sessió correctament amb l'administrador.

---
<img width="1019" height="767" alt="image" src="https://github.com/user-attachments/assets/b50e90a7-51cc-4390-b955-512d131e1820" />


# 4. Anàlisi Forense (Event Viewer)
1. Actueu com a pèrits informàtics per trobar les proves de l'intent d'intrusió anterior.
2. Obriu el Visor d'Esdeveniments (Event Viewer).

<img width="797" height="724" alt="image" src="https://github.com/user-attachments/assets/430445ea-b0f0-42a8-9b29-e71e923d787e" />

---
3. Aneu al registre de Seguretat. Busqueu els esdeveniments recents que corresponguin als vostres intents fallits.

<img width="1023" height="767" alt="image" src="https://github.com/user-attachments/assets/6bf774ec-c100-47ae-88fd-0c70968afaa5" />

---
4. Feu clic en un dels esdeveniments i mostreu-ne els detalls (usuari que ho ha intentat, hora, IP d'origen si n'hi ha).

---
<img width="674" height="499" alt="image" src="https://github.com/user-attachments/assets/edfcc78f-d7ac-4d1a-8b36-f76302d6f272" />

# Tasca d'investigació
## Localitzeu l'Event ID (identificador de l'esdeveniment) que correspon a un "intent d'inici de sessió fallit".

<img width="1019" height="767" alt="image" src="https://github.com/user-attachments/assets/e325409b-5a89-43b0-9805-5722f11927f2" />

---
Com es pot vuere, els primers tres logins són els intent de iniciar sessió amb el usuari de J.Fernandez, que té la ID de 5152 i despres el login de l'usuari administrador amb la ID de 5156.

