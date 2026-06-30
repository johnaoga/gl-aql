.. _part2_chap6:

***********************************************************************
Chapitre 6 : Métriques orientées objet (Chidamber & Kemerer)
***********************************************************************

Les métriques orientées objet évaluent **le code et sa structure**. Chidamber &
Kemerer ont proposé un ensemble de **six métriques** (les **métriques CK**)
couvrant la complexité d'une classe ou d'un objet.

.. note::
   Chapitre présenté en **exposé**.

Pourquoi des métriques OO ?
===========================

Elles permettent de :

- **mesurer la qualité du code** (complexité, couplage, cohésion, maintenabilité, lisibilité) ;
- **faciliter la maintenance** (repérer le code complexe, peu cohésif ou fortement couplé) ;
- **prendre des décisions** (réécriture, **refactorisation**, respect des normes) ;
- **améliorer la compréhensibilité** (identifier le code difficile à comprendre).


Les 6 métriques CK
==================

On illustre avec une classe ``Personne`` (attributs ``nom``, ``age`` ; méthodes
``setNom``, ``setAge``, ``getInfo``).

.. list-table::
   :header-rows: 1
   :widths: 14 46 40

   * - Métrique
     - Définition
     - Sur l'exemple ``Personne``
   * - **WMC** (Weighted Methods per Class)
     - Complexité de la classe = somme pondérée (par McCabe) de ses méthodes
     - WMC = 1 + 1 + 1 = **3**
   * - **DIT** (Depth of Inheritance Tree)
     - Profondeur de la classe dans l'arbre d'héritage (nb max d'ancêtres)
     - DIT = **0** (pas de classe parente)
   * - **NOC** (Number of Children)
     - Nombre de sous-classes **directes**
     - NOC = **0**
   * - **CBO** (Coupling Between Objects)
     - Nombre de classes couplées à la classe
     - CBO = **1** si une classe ``Adresse`` lui est couplée
   * - **RFC** (Response For a Class)
     - Méthodes locales + méthodes appelées en réponse à un message
     - RFC = **3**
   * - **LCOM** (Lack of Cohesion in Methods)
     - Manque de cohésion : (paires de méthodes non liées − paires liées) / 2
     - (1 − 2)/2 = −0,5 ⇒ ramené à **0** (``max(0, LCOM)``)

.. note::
   **Calcul de LCOM sur ``Personne``** — paires : (setNom, setAge) → aucun attribut
   commun (non liées) ; (setNom, getInfo) → ``nom`` (liées) ; (setAge, getInfo) →
   ``age`` (liées). LCOM = (1 − 2)/2 = −0,5, ramené à 0.


Interpréter les scores et agir
==============================

.. list-table::
   :header-rows: 1
   :widths: 18 14 12 12 22 22

   * - Métrique
     - Faible/Normal
     - Moyen
     - Élevé
     - Diagnostic
     - Actions possibles
   * - **WMC** (↔ McCabe)
     - ≤ 10
     - 11–20
     - > 20
     - Structure trop complexe
     - Refactoring (scinder, réécrire)
   * - **DIT**
     - ≤ 2
     - 3–4
     - > 4
     - Hiérarchie fragile
     - Refactoring (composer)
   * - **NOC**
     - ≤ 3
     - 4–6
     - > 6
     - Classe mère instable
     - Refactoring (abstraire)
   * - **CBO**
     - ≤ 5
     - 6–10
     - > 10
     - Couplage trop fort
     - Refactoring (regrouper, scinder)
   * - **RFC**
     - ≤ 20
     - 21–40
     - > 40
     - Trop de responsabilités
     - Refactoring (réécrire, scinder)
   * - **LCOM**
     - 0
     - > 0
     - ≫ 0
     - Faible cohésion
     - Refactoring (scinder)


Avantages, limites, difficulté d'utilisation
============================================

**Avantages** — identification des zones à risque ; orientation vers la qualité du
code ; aide à la décision ; réduction de la complexité ; amélioration de la
maintenance ; application généralisée.

**Limites**

- **Sensibilité à la taille des classes** : une grande classe peut sembler complexe même bien conçue ⇒ compléter par d'autres métriques.
- **Manque de contexte métier** : elles évaluent la structure, pas les exigences spécifiques d'un domaine.
- **Focus structure plutôt que comportement** : un code « bien noté » peut avoir des problèmes de performance/fonctionnalité à l'exécution ⇒ compléter par des tests fonctionnels et des mesures de performance.

**Difficulté en pratique** — elles nécessitent des informations détaillées sur la
**structure du code**, difficiles à obtenir sur de grands projets.


Exercice
========

Soit un code source fourni :

1. Calculez les **six métriques CK** (pour chaque classe et au total).
2. Interprétez les résultats (métriques les plus élevées et risques associés ; évaluation globale ; points d'attention).
3. Pour chaque métrique élevée, proposez une solution (selon votre choix de classe).
