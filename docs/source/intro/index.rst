.. _intro:

*********************
Organisation du cours
*********************

.. note::
   Si vous suivez ce cours actuellement, vous devez signer la charte d'utilisation de l'IA ici : https://forms.gle/TtNLyc4pNSYaANTX9

L'objectif de ce cours est d'aborder la notion de **qualité** d'un logiciel et de
voir comment **s'assurer** d'avoir un logiciel de qualité — en s'appuyant sur les
normes et standards internationaux (**ISO/IEC 9126**), en appliquant des
**métriques** logicielles, et en mettant en œuvre des processus de **test** et
d'**évaluation** sur des projets concrets.

À la fin de ce cours, l'étudiant.e doit être capable de :

* Distinguer un *bon logiciel* d'un *logiciel de qualité*, et l'**assurabilité** de la **testabilité**
* Expliquer les critères et sous-critères de qualité selon la norme **ISO/IEC 9126** (Capacité fonctionnelle, Fiabilité, Facilité d'utilisation, Rendement, Maintenabilité, Portabilité)
* Évaluer la qualité d'une application existante en appliquant systématiquement ces critères, avec exemples et justifications
* Comprendre la **théorie de la mesure** (réalité → modèle → mesure, échelles) pour quantifier la qualité sans subjectivité
* Appliquer les **métriques** logicielles (McCabe & Big O, Point Fonction & Bang, métriques OO de Chidamber & Kemerer, cohésion & couplage)
* Concevoir des stratégies de **test** et assurer la **testabilité** d'un système
* Présenter de manière structurée et argumentée une analyse de qualité logicielle


Pédagogie
=======================================

La pédagogie est mixte et basée sur l'**apprentissage par projet**. Nous alternerons :

* Des cours magistraux pour clarifier les concepts et présenter la norme ISO/IEC 9126
* Des travaux pratiques d'**évaluation** d'applications existantes (tableau de qualité)
* Des **exposés de groupe** pour présenter et appliquer les métriques logicielles
* Un **projet** combinant assurabilité et testabilité, avec **évaluation croisée** entre équipes

Par conséquent, les étudiants doivent travailler régulièrement, en équipe, pour
développer leur projet d'évaluation et d'amélioration de la qualité logicielle.


Répartition du cours
=======================================

Le cours est organisé en parties, chacune composée de plusieurs chapitres :

* :doc:`Partie 1 <../part1/index>` — **Préliminaires** : qualité d'un logiciel, assurabilité vs testabilité, et la norme ISO/IEC 9126.
* :doc:`Partie 2 <../part2/index>` — **Les mesures** : théorie de la mesure et les grandes familles de métriques logicielles.
* :doc:`Partie 3 <../part3/index>` — **Projet** : assurance et testabilité de la qualité, en évaluation croisée.

Une partie :doc:`QCM <../part6/index>` interactive complète le cours.


Déroulé des séances
=======================================

Le cours alterne cours, exposés de groupe (une famille de métriques par groupe) et
travail de projet. Les dates exactes sont communiquées par l'enseignant.

.. list-table::
   :header-rows: 1
   :widths: 12 53 35
   :class: longtable

   * - Séance
     - Contenu
     - Travaux / Exposés / Projet
   * - Séance 1
     - **Chapitre 0–1** : qualité d'un logiciel ; assurabilité, testabilité, subjectivité → la norme
     - Mise en situation
   * - Séance 2
     - **Chapitre 2** : norme ISO/IEC 9126 (6 critères, exemple Word)
     - Tableau d'évaluation (TP individuel) lancé
   * - Séance 3
     - **Chapitre 3** : modèles et mesures (réalité → modèle → mesure, échelles)
     - Tableau rendu · projets lancés
   * - Séances 4 à 7
     - **Chapitres 4–7** : exposés des familles de métriques (McCabe/Big O, Point Fonction & Bang, OO/CK, cohésion & couplage) + restructuration
     - Exposés évalués · projet (assurance/testabilité)
   * - Séance 8
     - **Chapitre 8** : récapitulatif (synthèse des métriques ↔ critères ISO)
     - Projet
   * - Séances suivantes
     - Suivi de projet et **évaluation croisée**
     - Rendus assurabilité & testabilité

.. note::
   Chaque famille de métriques est présentée par un **groupe** (exposé) ; après
   chaque présentation, une **restructuration** (mise au propre) est faite.


Évaluation
=======================================

L'évaluation comporte quatre éléments (les trois derniers se font **en groupe**) :

.. list-table::
   :header-rows: 1
   :widths: 70 15

   * - Élément
     - Poids
   * - **Tableau individuel** — évaluation de la qualité d'une application existante selon ISO/IEC 9126
     - **25 %**
   * - **Présentation (exposé)** — une famille de métriques appliquée, reliée aux critères ISO/IEC 9126
     - **25 %**
   * - **Projet — Assurabilité** — concevoir/assurer la qualité d'un logiciel
     - **25 %**
   * - **Projet — Testabilité** — concevoir les tests et évaluer la qualité d'un projet tiers (table de test)
     - **25 %**

**Note finale = 25 % Tableau individuel + 25 % Présentation + 25 % Projet Assurabilité + 25 % Projet Testabilité.**

.. note::
   Le détail des livrables et de l'**évaluation croisée** (chaque thème de projet a
   un groupe *assurabilité* et un groupe *testabilité*) figure dans la
   :doc:`Partie 3 — Projet <../part3/index>`.


Contact et communication
=======================================

Les communications se feront par mail.

:Email: `John Aoga <johnaoga@gmail.com>`_


Cours Open-Source
=======================================

Les sources de ce site web sont open-source et disponibles sur `GitHub <https://github.com/johnaoga/gl-aql>`_.
N'hésitez pas à faire des pull requests si vous voyez des erreurs ou des éléments à corriger.

La licence utilisée est Creative Commons Attribution-ShareAlike 4.0 International License :

.. image:: https://i.creativecommons.org/l/by-sa/4.0/88x31.png
    :alt: CC-BY-SA
