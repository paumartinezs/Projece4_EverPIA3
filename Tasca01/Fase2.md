# **T01: DRP: còpies de seguretat. Estudi cas client (treball cooperatiu)**

**(Parelles)**

**Fase 2: Treball per parelles**

Treballant per parelles:

1\.       Discussió i Consens: Comparen les seves respostes individuals (Fase 1).

2\.     Elaboració d'una Proposta Unificada: Heu de consensuar i dissenyar el vostre propi Esquema 3-2-1 de Còpies (3 còpies, 2 mitjans, 1 fora de lloc) basat en els requisits del cas.

| Element | Proposta de la Parella | Justificació / Observacions |
| :---- | :---- | :---- |
| **Dades Crítiques** | Bases de dades Documents compartits/projectes, Carpetes personals d'usuari, Carpetes dels tècnics. | Les dades de major impacte són les que afecten l'operativa i la gestió. S'opta per la centralització al servidor i només es cobreixen les carpetes crítiques localitzades als clients. |
| **Periodicitat (BD)** | **Diària:** Dilluns \- Dijous.  **Setmanal:** Divendres o         Diumenge. **Mensual:** Primer diumenge de mes. | Calendari equilibrat que combina rapidesa de còpia amb eficiència d’espai. Redueix el mantenint punts de recuperació freqüents. |
| **Tipus de Còpia (BD)** | **Diària:** Incremental.  **Setmanal:** Diferencial. **Mensual:** Completa. | Incrementals són més ràpides i lleugeres diàriament. Diferencial simplifica les restauracions de final de setmana. Completa serveix com a punt base robust per a retenció i desastres. |
| **Mitjà 1 (Local)** | **NAS local** | Ofereix alta velocitat per complir un RTO objectiu de menys de 4 hores. Ideal per a còpies diàries i setmanals, permetent una restauració immediata. |
| **Mitjà 2 (Extern)** | **Cloud Storage** Emmagatzematge Objecte | Garanteix l'emmagatzematge fora de lloc per complir la regla 3-2-1. Ideal per a còpies mensuals i retenció prolongada. Protecció davant de desastres físics. |

[Torna a l'enunciat](README.md)

[Torna a la pàgina principal](../REAMDE.md)
