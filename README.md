# PerfoAvion + Système de conduite du vol (FGS)

**École Nationale de l’Aviation Civile (ENAC)**  
[www.enac.fr](https://www.enac.fr)

## Description du projet
Ce projet implémente le **module FGS (Flight Guidance System / Système de conduite du vol)** pour un avion, basé sur un exemple réel comme l’A320. Il combine **perfo avion** et **gestion du vol**.  

Le module FGS assure :  
- L’envoi du vent et de la déclinaison magnétique sur le bus.  
- La gestion de la configuration de l’avion, notamment les volets.  
- Le calcul en permanence, selon la configuration avion et l’altitude :  
  - **Vitesse indiquée (Vi) consigne** pour le FGS.  
  - **Angle de roulis maximum** à ne pas dépasser.  

## Fonctionnalités
- **Lecture et traitement du plan de vol** :  
  - Liste de points sous la forme `[WayPointName, x, y, z, overFly/flyBy]`.  
  - `z = -1` si pas de consigne de niveau sur le WayPoint.  
  - Format IVY pour affichage :  
    ```
    FplWpts Waypoints=NAME1;X;Y;Z|NAME2;X;Y;Z...
    ```  
  - Envoi du **vecteur d’état initial** (1er point du plan de vol).  

- **Calcul des modes et consignes associées** :  
  - **Modes managés** :  
    - Latéral : capture d’axe.  
    - Vertical : capture d’altitude.  
    - Vitesse : capture de la vitesse indiquée ou du Mach selon l’altitude (`z`).  
  - Les autres modes sont **sélectionnés au FCU (Flight Control Unit)**.  
  - Gestion de la commande **DIRTO**, pour diriger l’avion directement vers un WayPoint.  


## Technologies utilisées
- Python 3.x  
- Librairie IVY (communication avionique)  
- Scripts de tests automatisés en Python  

## Auteur
****  
École Nationale de l’Aviation Civile (ENAC)  

## Licence




