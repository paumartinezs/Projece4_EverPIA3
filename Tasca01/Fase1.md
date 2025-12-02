
# **Fase 1: Treball individual**

De forma individual, heu de donar resposta a les següents preguntes basant-se en el cas pràctic:

## 1\.    Què copiar? (Priorització): Quines són les dades més crítiques del servidor? Cal fer còpia dels 10 equips clients? Justifica-ho.

- Les dades més crítiques del servidor són les bases de dades, els documents compartits i les configuracions  
- No és necessari fer 10 equips, clients ja que la informació crítica ha d'estar agrupada al servidor

## 2\. Periodicitat i Tipus de Còpia: Proposa un calendari bàsic per a la setmana (Diari/Setmanal/Mensual) i quin tipus de còpia aplicaràs (Completa, Diferencial, Incremental) per a les dades crítiques.

| Periodicitat | Freqüència | Tipus de Còpia | Funció |
| :---- | :---- | :---- | :---- |
| **Diari** | De Dilluns a Divendres | **Incremental** | Copia els canvis fets des de l'última còpia Completa (Diumenge). |
| **Setmanal** | Diumenge | **Diferencial** | Crea un punt base complet de totes les dades. |
| **Mensual** | Primer Diumenge | **Completa**  | Còpia destinada a emmagatzematge a llarg termini |

## 3\.   Mitjans i Ubicació: Quin tipus de mitjà de còpia utilitzaries (Discs durs externs, NAS, Cloud, Cintes)? On s'hauria de guardar físicament la còpia més recent (Regla 3-2-1).

**Mitjans de copies:**

1. **NAS:** (Network attached Storage): Per a la copia diaria (rapida) i setmanal.  
2. **CLOUD:** (emmagatzematge objecte): Per a la copia fora de les instal·lacions

**Ubicació de la Còpia Més recent:**

- **La còpia diària diferencial** es guardarà al NAS per permetre una recuperació immediata de fitxers  
- **La còpia mensual completa** es guardarà al cloud com a còpia de seguretat per a la recuperació de desastres

[Torna a l'enunciat](README.md)

[Torna a la pàgina principal](../README.md)
