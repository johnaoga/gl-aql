.. _part3:

*************************************************************************************************
Partie 3 | Projet : Assurance et Testabilité de la Qualité des Logiciels
*************************************************************************************************

Objectifs
=========

À l'issue de cette partie, chaque étudiant.e sera capable de :

* S'assurer qu'un logiciel est **de qualité** (assurabilité) en appliquant ISO/IEC 9126 et les métriques
* Concevoir et appliquer des **stratégies de test** (testabilité) sur un logiciel tiers
* Évaluer objectivement la qualité d'un projet tiers et communiquer les résultats de façon constructive

.. admonition:: Attention
   :class: important

   Il ne s'agit **pas** d'un projet de développement pur : ce sont les aspects
   **assurabilité** et **testabilité** (A/TQL) qui sont évalués en priorité.


Le principe : l'évaluation croisée
==================================

Chaque **thème de projet** est traité par **deux groupes** dans des rôles
complémentaires :

- un groupe **Assurabilité** — conçoit/réalise le logiciel et **assure** sa qualité
  (ISO/IEC 9126 + métriques) ;
- un groupe **Testabilité** — conçoit les **tests** du logiciel de l'autre groupe et
  **évalue** sa qualité (table de test).

Ainsi, chaque groupe est tour à tour **producteur** (assurabilité de son thème) et
**évaluateur** (testabilité d'un autre thème). Cela développe l'esprit critique et
la communication constructive des résultats.

.. list-table:: Exemple de répartition croisée (illustratif)
   :header-rows: 1
   :widths: 50 25 25

   * - Thème
     - Assurabilité
     - Testabilité
   * - Thème A
     - Groupe 1
     - Groupe 3
   * - Thème B
     - Groupe 2
     - Groupe 1
   * - Thème C
     - Groupe 3
     - Groupe 4
   * - Thème D
     - Groupe 4
     - Groupe 2

.. note::
   Les **thèmes** précis, la **répartition** des groupes et les **dates** de rendu
   sont communiqués par l'enseignant chaque année. Les sujets portent typiquement
   sur des plateformes réalistes (ex. plateforme de cours en ligne, générateur de
   sites d'événements, gestion d'emplois du temps/salles, robotarium, etc.).


Livrables
=========

**Côté assurabilité**

- **Rapport** de projet — description du projet, *use cases*, présentation du
  résultat, démarche AQL appliquée — **10 pages max** (hors intro, conclusion, références) ;
- **Vidéo** courte de fonctionnement du logiciel — **5 min max** ;
- **Code** + petite **documentation** (développeur + utilisateur).

**Côté testabilité**

- **Table de test** du logiciel à tester (cas de test, résultats attendus/obtenus,
  verdicts), accompagnée d'une évaluation de la qualité.


Évaluation
==========

.. list-table::
   :header-rows: 1
   :widths: 70 15

   * - Élément
     - Poids
   * - **Tableau individuel** — qualité d'une application existante (ISO/IEC 9126)
     - 25 %
   * - **Présentation (exposé)** — une famille de métriques appliquée
     - 25 %
   * - **Projet — Assurabilité**
     - 25 %
   * - **Projet — Testabilité**
     - 25 %

**Grille d'évaluation du projet**

.. list-table::
   :header-rows: 1
   :widths: 26 18 18 19 19

   * - Critère
     - Insuffisant
     - Correct
     - Bien
     - Excellent
   * - **Assurabilité (ISO 9126 + métriques)**
     - Démarche absente
     - Critères évalués partiellement
     - Évaluation correcte et justifiée
     - Évaluation complète, métriques à l'appui
   * - **Testabilité (table de test)**
     - Pas de tests
     - Tests superficiels
     - Tests pertinents et structurés
     - Couverture large, verdicts clairs
   * - **Logiciel & documentation**
     - Non fonctionnel / non documenté
     - Partiel
     - Fonctionnel et documenté
     - Soigné (code + doc dev/user)
   * - **Communication (rapport, vidéo, retours)**
     - Absente / confuse
     - Acceptable
     - Claire
     - Claire, constructive et professionnelle


Conseils
========

1. Commencez tôt ; gardez la trace de votre démarche AQL au fur et à mesure.
2. Reliez chaque constat de qualité à un **critère ISO/IEC 9126** et, si possible, à une **métrique** (Partie 2).
3. Côté testabilité, soyez **objectifs et constructifs** : la table de test sert à améliorer, pas à juger.

.. note::
   Les dates de rendu (et la remise au groupe évaluateur) sont fixées par
   l'enseignant en début de projet.
