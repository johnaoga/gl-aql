.. _part5:


*************************************************************************************************
Chapitre 5 | Évaluation croisée et amélioration continue
*************************************************************************************************

Objectifs
=========

À l'issue de ce module, chaque étudiant.e sera capable de :

* Évaluer objectivement un projet développé par une autre équipe
* Appliquer les critères de testabilité et d'assurabilité sur un projet tiers
* Identifier les points d'amélioration et proposer des solutions concrètes
* Communiquer les résultats d'évaluation de manière constructive
* Appliquer une démarche d'amélioration continue dans l'assurance qualité
* Réceptionner et intégrer des retours critiques sur son propre travail


Note de théorique
=======================================

1. Introduction à l'évaluation croisée
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Définition :** L'évaluation croisée est un processus où une équipe évalue le travail d'une autre équipe selon des critères objectifs et standardisés.

**Objectifs :**

* Développer l'esprit critique et analytique
* Identifier les bonnes pratiques et les axes d'amélioration
* Favoriser l'apprentissage par l'observation
* Créer une culture de qualité partagée
* Améliorer la collaboration entre équipes


**Principes fondamentaux :**

* **Objectivité** : S'appuyer sur des critères mesurables et la norme ISO/IEC 9126
* **Constructivité** : Proposer des solutions, pas seulement identifier des problèmes
* **Professionnalisme** : Fournir des retours structurés et documentés


2. Méthodologie d'évaluation croisée
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**2.1. Préparation de l'évaluation**

**Étape 1 : Comprendre le contexte du projet**

* Lire la documentation fournie
* Identifier les objectifs et les exigences du projet
* Comprendre les choix technologiques
* Définir le périmètre de l'évaluation

**Étape 2 : Définir les critères d'évaluation**

Utiliser une grille basée sur :

* Les 6 critères ISO/IEC 9126
* Les métriques logicielles (complexité, couplage, cohésion)
* La testabilité et l'assurabilité
* Les bonnes pratiques de développement


**2.2. Conduite de l'évaluation**

**Analyse du code source**

* Structure et organisation du projet
* Qualité du code (lisibilité, conventions)
* Architecture et design patterns
* Gestion des erreurs et exceptions
* Sécurité

**Analyse de la testabilité**

* Présence et qualité des tests
* Couverture de code
* Complexité cyclomatique
* Injection de dépendances
* Isolation des composants

**Analyse de l'assurabilité**

* Documentation technique
* Traçabilité des exigences
* Processus de revue de code
* Respect des normes et standards
* Maintenabilité globale

**Calcul des métriques**

* Complexité cyclomatique moyenne
* Couplage (CBO)
* Cohésion (LCOM)
* Profondeur d'héritage (DIT)
* Taille des méthodes


**2.3. Documentation des résultats**

Le rapport d'évaluation doit contenir :

1. **Résumé exécutif** (1 page)
   
   * Appréciation générale du projet
   * Note globale selon ISO/IEC 9126
   * 3 points forts principaux
   * 3 axes d'amélioration prioritaires

2. **Évaluation détaillée par critère ISO/IEC 9126**
   
   * Tableau récapitulatif avec notes et justifications
   * Exemples concrets tirés du code
   * Références aux fichiers et lignes de code

3. **Analyse de la testabilité**
   
   * Grille d'évaluation complétée
   * Métriques calculées
   * Observations et recommandations

4. **Analyse de l'assurabilité**
   
   * Évaluation de la documentation
   * Processus de qualité en place
   * Conformité aux bonnes pratiques

5. **Recommandations priorisées**
   
   * Liste des améliorations proposées
   * Priorisation (Critique / Important / Souhaitable)
   * Solutions concrètes et actionnables
   * Estimation de l'effort de correction


3. Grilles d'évaluation standardisées
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**3.1. Grille globale ISO/IEC 9126**

+--------------------------------+--------+------------------+------------------------+
| **Critère**                    | **/5** | **Exemples**     | **Recommandations**    |
+================================+========+==================+========================+
| Capacité fonctionnelle         |        |                  |                        |
+--------------------------------+--------+------------------+------------------------+
| Fiabilité                      |        |                  |                        |
+--------------------------------+--------+------------------+------------------------+
| Utilisabilité                  |        |                  |                        |
+--------------------------------+--------+------------------+------------------------+
| Efficacité                     |        |                  |                        |
+--------------------------------+--------+------------------+------------------------+
| Maintenabilité                 |        |                  |                        |
+--------------------------------+--------+------------------+------------------------+
| Portabilité                    |        |                  |                        |
+--------------------------------+--------+------------------+------------------------+
| **Score total**                | **/30**|                  |                        |
+--------------------------------+--------+------------------+------------------------+


**3.2. Grille de testabilité**

+----------------------------------+--------+------------------+-------------+
| **Critère**                      | **/5** | **Valeur**       | **Priorité**|
+==================================+========+==================+=============+
| Couverture de tests              |        | __%              |             |
+----------------------------------+--------+------------------+-------------+
| Qualité des tests                |        |                  |             |
+----------------------------------+--------+------------------+-------------+
| Injection de dépendances         |        |                  |             |
+----------------------------------+--------+------------------+-------------+
| Complexité cyclomatique moyenne  |        |                  |             |
+----------------------------------+--------+------------------+-------------+
| Couplage moyen (CBO)             |        |                  |             |
+----------------------------------+--------+------------------+-------------+
| Taille moyenne des méthodes      |        | __ lignes        |             |
+----------------------------------+--------+------------------+-------------+
| Isolation des composants         |        |                  |             |
+----------------------------------+--------+------------------+-------------+
| **Score total**                  | **/35**|                  |             |
+----------------------------------+--------+------------------+-------------+


**3.3. Grille d'assurabilité**

+----------------------------------+--------+------------------+-------------+
| **Critère**                      | **/5** | **Observation**  | **Action**  |
+==================================+========+==================+=============+
| Documentation technique          |        |                  |             |
+----------------------------------+--------+------------------+-------------+
| Architecture documentée          |        |                  |             |
+----------------------------------+--------+------------------+-------------+
| Commentaires dans le code        |        |                  |             |
+----------------------------------+--------+------------------+-------------+
| Traçabilité exigences-tests      |        |                  |             |
+----------------------------------+--------+------------------+-------------+
| Conventions de code respectées   |        |                  |             |
+----------------------------------+--------+------------------+-------------+
| Gestion des versions (Git)       |        |                  |             |
+----------------------------------+--------+------------------+-------------+
| README complet                   |        |                  |             |
+----------------------------------+--------+------------------+-------------+
| **Score total**                  | **/35**|                  |             |
+----------------------------------+--------+------------------+-------------+


4. Communication des résultats
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

 **Rapport écrit**

**Format du rapport :**

.. code-block:: text

    RAPPORT D'ÉVALUATION CROISÉE
    
    ═══════════════════════════════════════
    INFORMATIONS GÉNÉRALES
    ═══════════════════════════════════════
    Projet évalué     : [Nom du projet]
    Équipe évaluée    : [Noms des membres]
    Équipe évaluatrice: [Noms des membres]
    Date d'évaluation : [Date]
    
    ═══════════════════════════════════════
    RÉSUMÉ EXÉCUTIF
    ═══════════════════════════════════════
    
    Note globale: __/100
    
    Points forts:
    1. [Point fort 1]
    2. [Point fort 2]
    3. [Point fort 3]
    
    Axes d'amélioration prioritaires:
    1. [Amélioration 1]
    2. [Amélioration 2]
    3. [Amélioration 3]
    
    ═══════════════════════════════════════
    ÉVALUATION ISO/IEC 9126
    ═══════════════════════════════════════
    [Tableau détaillé]
    
    ═══════════════════════════════════════
    ANALYSE DE LA TESTABILITÉ
    ═══════════════════════════════════════
    [Grille complétée + analyse]
    
    ═══════════════════════════════════════
    ANALYSE DE L'ASSURABILITÉ
    ═══════════════════════════════════════
    [Grille complétée + analyse]
    
    ═══════════════════════════════════════
    PROBLÈMES IDENTIFIÉS (TOP 5)
    ═══════════════════════════════════════
    
    1. [Problème 1]
       - Localisation: [Fichier:ligne]
       - Impact: [Critique/Important/Mineur]
       - Explication: [...]
       - Recommandation: [...]
    
    [...]
    
    ═══════════════════════════════════════
    RECOMMANDATIONS PRIORISÉES
    ═══════════════════════════════════════
    [Liste détaillée avec priorités]
    
    ═══════════════════════════════════════
    CONCLUSION
    ═══════════════════════════════════════
    [Synthèse finale]



7. Bonnes pratiques d'évaluation croisée
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**DO (À faire) :**

✓ S'appuyer sur des critères objectifs et mesurables
✓ Fournir des exemples concrets de code
✓ Proposer des solutions actionnables
✓ Commencer par les points positifs
✓ Utiliser un langage professionnel et bienveillant
✓ Référencer des ressources et documentation
✓ Prioriser les recommandations
✓ Documenter de manière structurée

**DON'T (À éviter) :**

✗ Porter des jugements personnels
✗ Être vague ou général sans exemples
✗ Ne pointer que les problèmes sans solutions
✗ Utiliser un ton agressif ou condescendant
✗ Ignorer le contexte du projet
✗ Être trop exhaustif (se concentrer sur l'essentiel)
✗ Comparer négativement avec d'autres équipes


À lire / Aller plus loin
=======================================

Slides du cours :

Livres de référence :


Aller plus loin :



Exercices théoriques
=======================================

.. note::
    Ces exercices constituent l'évaluation finale du module. Ils doivent être réalisés avec rigueur et professionnalisme.


Exercice - Analyse préliminaire
""""""""""""""""""""""""""""""""""

Vous allez recevoir le code source d'un projet développé par une autre équipe. Avant l'évaluation complète :

Réalisez une évaluation complète du projet selon la méthodologie du cours :

1. **Évaluation ISO/IEC 9126** (30%)
   
   * Remplissez la grille d'évaluation des 6 critères
   * Fournissez des exemples concrets pour chaque critère
   * Justifiez vos notes avec des références au code

2. **Analyse de la testabilité** (35%)
   
   * Calculez la couverture de tests (si disponible)
   * Mesurez la complexité cyclomatique moyenne
   * Évaluez le couplage (CBO) et la cohésion (LCOM)
   * Analysez la présence d'injection de dépendances
   * Vérifiez la taille moyenne des méthodes

3. **Analyse de l'assurabilité** (35%)
   
   * Évaluez la qualité de la documentation
   * Vérifiez la traçabilité des exigences
   * Analysez l'architecture et sa documentation
   * Évaluez le respect des conventions de code
   * Vérifiez la gestion des versions (commits Git)

**Livrables :**

* Rapport d'évaluation complet (10 pages au plus )
* Grilles d'évaluation remplies
* Recommandations priorisées

