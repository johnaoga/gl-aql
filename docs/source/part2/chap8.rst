.. _part2_chap8:

***********************************************************************
Chapitre 8 : Récapitulatif
***********************************************************************

Ce chapitre synthétise les familles de métriques et les relie aux critères de
qualité de la :doc:`norme ISO/IEC 9126 <../part1/chap2>`.

Synthèse des métriques
======================

.. list-table::
   :header-rows: 1
   :widths: 26 14 36 24

   * - Famille
     - Point de vue
     - Ce qu'elle mesure
     - Critère(s) ISO/IEC 9126
   * - **McCabe** (complexité cyclomatique)
     - Code
     - Complexité structurelle du flot de contrôle
     - Maintenabilité (analyse, testabilité)
   * - **Big O**
     - Code
     - Croissance du temps/mémoire (efficacité)
     - Rendement
   * - **Point Fonction (FPA)**
     - Utilisateur
     - Taille **fonctionnelle** (indépendante du code)
     - Capacité fonctionnelle
   * - **Métriques de Bang (De Marco)**
     - Technique
     - Complexité structurelle / connectivité du code
     - Rendement, maintenabilité
   * - **Métriques OO (CK)** : WMC, DIT, NOC, CBO, RFC, LCOM
     - Code / conception
     - Complexité, héritage, couplage, cohésion d'une classe
     - Maintenabilité, portabilité
   * - **Cohésion & couplage**
     - Conception / code
     - Cohésion interne, interdépendance entre modules
     - Maintenabilité, portabilité, testabilité


Comment choisir une métrique ?
==============================

- On veut estimer la **taille** d'un besoin, indépendamment du code ? → **Point Fonction**.
- On veut juger l'**efficacité** d'un algorithme ? → **Big O**.
- On veut repérer le code **trop complexe** à tester/maintenir ? → **McCabe**, **WMC**.
- On veut évaluer la **conception OO** (héritage, couplage, cohésion) ? → **métriques CK**, **cohésion & couplage**.

.. admonition:: À retenir
   :class: important

   Aucune métrique ne suffit seule : elles se **complètent**. On les choisit selon
   le **critère ISO/IEC 9126** que l'on cherche à objectiver, et on les **interprète**
   (seuils, diagnostic) avant de proposer des **actions** (refactoring).


Pour aller plus loin
====================

Testez vos acquis avec les :doc:`QCM interactifs <../part6/index>`, puis appliquez
ces métriques dans le :doc:`projet <../part3/index>`.
