### T07: Accés remot. Serveis d’assistència remota (tasca en parelles)


Fins ara hem vist eines per administrar servidors (**SSH, RDP, VNC**). Però la realitat de la nostra feina a **EverPia** és que una gran part de les nostres hores facturables provenen del **suport directe a l'usuari final (Helpdesk)**.

Quan un client truca perquè *"el PDF no s'obre"*, *"li ha desaparegut una icona"* o *"la impressora no imprimeix"*, no li podem demanar que configuri una VPN o obri el port 3389 del seu router. Necessitem una **eina d'assistència remota sota demanda**: ràpida, fiable, segura i que funcioni en segons, fins i tot en xarxes restrictives.

---

## Objectiu del projecte

La direcció d'EverPia ha decidit estandarditzar l’eina oficial que farem servir per a aquestes tasques de suport immediat. La vostra missió en parelles és:

- Analitzar el mercat  
- Proposar la millor solució  
- Crear la documentació que utilitzaran tant tècnics com clients  

---

# Fase 1: Anàlisi Comparativa i Selecció de la Solució

El primer pas és decidir **quina eina utilitzarà EverPia**. Heu de fer una anàlisi de mercat i presentar un informe comparatiu breu.

## Tasques

### 1. Investigar quatre alternatives populars d'assistència remota

**Obligatòries:**
- TeamViewer  
- AnyDesk  
- Google Remote Desktop  

**+ Afegir una quarta eina de la vostra elecció.**

---

### 2. Crear una Taula Comparativa amb els criteris següents:

- **Facilitat d'ús (per al client):**
  - Requereix instal·lació?
  - És portable?
  - Com de senzill és passar-nos l’ID?

- **Disponibilitat (Sistemes Operatius):**
  - Funciona a Windows?
  - macOS?
  - Linux?  
  *(Vital per a EverPia: donem suport a entorns mixtos).*

- **Model de Preu (Llicència):**
  - És gratuït per a ús comercial?
  - Preu d’una llicència tècnica?
  - Limitacions de la versió gratuïta?

---

### 3. Presentar una Recomanació

Basada en la taula comparativa, heu de recomanar oficialment **una de les eines** per ser adoptada a EverPia.

La recomanació ha d’incloure arguments sobre:
- Facilitat d’ús
- Funcionalitat tècnica
- Cost
- Fiabilitat i compatibilitat

---

# Fase 2: Creació de les Guies d’Ús (Documentació)

Un cop heu seleccionat l'eina a la Fase 1, heu de crear la documentació oficial del seu ús. Aquest material és essencial i tindrà **dos enfocaments diferents**:

---

## 📘 Guia 1: Manual per al Tècnic (Intern d’EverPia)

Guia destinada a becaris i tècnics que s'incorporin a l’empresa.

**Ha d’incloure (amb captures de pantalla):**

- Com instal·lar la versió completa / tècnica de l’eina  
- Com iniciar una sessió de suport  
- Com gestionar funcions clau:
  - Transferència d’arxius
  - Canvi de pantalla
  - Reinici remot  
- Bones pràctiques de seguretat:
  - Tancar sempre la sessió  
  - No desar contrasenyes de clients  
  - Confirmar identitat abans de connectar  

---

## 🧑‍💻 Guia 2: Manual per al Client (Usuari Final)

Aquesta és la guia que enviarem als clients quan tinguin una incidència.  
Ha de ser **extremadament simple, visual i no tècnica**.

**Ha d’explicar (amb captures molt clares):**

- On descarregar el mòdul *Quick Support* (o equivalent)  
- On han de fer clic exactament  
- Com identificar i comunicar:
  - L’ID de sessió  
  - La contrasenya (si n'hi ha)  
- Com acceptar la sol·licitud de connexió  

---

## ✔ Objectiu final

Crear un sistema de suport remot eficient, estandarditzat i fàcil d'utilitzar tant per als clients com per als tècnics

---

  - [GuiaClients](GuiaClients.md)
  - [GuiaInterna](GuiaInterna.md)
