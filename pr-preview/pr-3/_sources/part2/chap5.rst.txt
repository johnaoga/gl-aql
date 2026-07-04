.. _part2_chap5:

***********************************************************************
Chapitre 5 : Point Fonction & métriques de Bang (De Marco)
***********************************************************************

Les métriques logicielles visent à **mesurer, estimer et comparer** des systèmes.
Ici deux approches opposées :

- le **Point Fonction (FPA)** — métrique de **taille fonctionnelle** ⇒ capacité fonctionnelle ;
- les **métriques de Bang (De Marco)** — **complexité structurelle du code** ⇒ rendement.

.. list-table::
   :header-rows: 1
   :widths: 50 25 25

   * - Critère
     - Point Fonction
     - Métriques de Bang
   * - Dépend du code
     - Non
     - Oui
   * - Dépend du langage
     - Non
     - Oui
   * - Mesure la complexité technique
     - Non
     - Oui
   * - Tient compte des spécifications (cahier des charges, fiche technique)
     - Oui
     - Non
   * - Mesure la taille fonctionnelle
     - Oui
     - Non
   * - Point de vue
     - Utilisateur
     - Technique / développeur

.. note::
   Chapitre présenté en **exposé**.


Le Point Fonction (Function Point Analysis)
===========================================

Le **Point Fonction (PF)** mesure la **taille fonctionnelle** d'un logiciel —
*ce que le système fait pour l'utilisateur*, indépendamment de la solution
technique. Il est donc :

- indépendant du **langage** ;
- indépendant de l'**architecture** ;
- indépendant du **nombre de lignes de code** ;
- basé **uniquement sur les spécifications fonctionnelles**.

.. note::
   Deux implémentations techniques différentes d'un même besoin utilisateur ont
   **le même nombre de points fonction**.

Le calcul repose sur cinq types de fonctions.

**Fonctions transactionnelles**

.. list-table::
   :header-rows: 1
   :widths: 12 30 58

   * - Type
     - Nom
     - Description
   * - **EI**
     - External Input
     - Entrée de données modifiant un état interne
   * - **EO**
     - External Output
     - Sortie avec traitement ou calcul
   * - **EQ**
     - External Inquiry
     - Requête simple sans mise à jour

**Fonctions de données**

.. list-table::
   :header-rows: 1
   :widths: 12 30 58

   * - Type
     - Nom
     - Description
   * - **ILF**
     - Internal Logical File
     - Données internes maintenues par le système
   * - **EIF**
     - External Interface File
     - Données externes référencées

Pondérations standard (IFPUG)
-----------------------------

.. list-table::
   :header-rows: 1
   :widths: 28 24 24 24

   * - Type
     - Faible
     - Moyen
     - Élevé
   * - EI
     - 3
     - 4
     - 6
   * - EO
     - 4
     - 5
     - 7
   * - EQ
     - 3
     - 4
     - 6
   * - ILF
     - 7
     - 10
     - 15
   * - EIF
     - 5
     - 7
     - 10

Classification : DET, FTR, RET
------------------------------

.. list-table::
   :header-rows: 1
   :widths: 14 36 26 24

   * - Notion
     - Définition
     - Exemple
     - Contre-exemple
   * - **DET** (Data Element Type)
     - Champ élémentaire reconnu par l'utilisateur, non dérivé automatiquement
     - nom, prénom, date, statut, montant, code
     - index, clés étrangères, champs calculés/techniques invisibles
   * - **FTR** (File Type Reference)
     - un ILF ou EIF lu/modifié par une fonction transactionnelle
     -
     - fichiers de config, logs d'erreurs
   * - **RET** (Record Element Type)
     - un sous-ensemble logique reconnu par l'utilisateur
     - Facture (ligne de facture), commande (ligne de commande)
     - client (client de base, adresse)

**Classification des EI**

.. list-table::
   :header-rows: 1
   :widths: 28 24 24 24

   * - EI
     - FTR = 0–1
     - FTR = 2
     - FTR ≥ 3
   * - DET 1–4
     - Faible
     - Faible
     - Moyen
   * - DET 5–15
     - Faible
     - Moyen
     - Élevé
   * - DET ≥ 16
     - Moyen
     - Élevé
     - Élevé

**Classification des ILF**

.. list-table::
   :header-rows: 1
   :widths: 28 24 24 24

   * - ILF
     - 1–19 DET
     - 20–50 DET
     - ≥ 51 DET
   * - 1 RET
     - Faible
     - Faible
     - Moyen
   * - 2–5 RET
     - Faible
     - Moyen
     - Élevé
   * - ≥ 6 RET
     - Moyen
     - Élevé
     - Élevé

.. admonition:: Exemple — ILF *Commande*
   :class: tip

   RET : *Commande* (numéro, date, client, total, adresse) + *Ligne de commande*
   (produit, quantité, prix, TVA, total) → **2 RET** ; **12 DET** ⇒ complexité
   **faible** ⇒ contribution **7 PF**.

Calcul du nombre de points fonction
-----------------------------------

Nombre de fonctions non ajusté (UFC) :

.. math::

   UFC = \sum_{i} (\text{nombre de fonctions}_i \times \text{poids}_i)

Facteur de complexité technique (TFC), basé sur **14 caractéristiques générales**
notées de 0 à 5 :

.. math::

   TFC = 0.65 + 0.01 \times \sum_{i=1}^{14} GSC_i

Point Fonction final :

.. math::

   PF = UFC \times TFC


Les métriques de Bang (De Marco)
================================

Ensemble de mesures basées sur la **théorie des graphes**, du **point de vue
technique (code)** :

- mesurent la **complexité structurelle** et la **connectivité** d'un programme ;
- permettent d'identifier les **zones à risque** ;
- deux catégories : métriques de **complexité** (lignes de code, variables,
  fonctions…) et métriques de **connectivité** (chemins, cycles…).
- exemples : *Cyclomatic Complexity* (CC), *Number of Lines of Code* (LOC),
  *Number of Modules* (NM).


Exercice
========

Soit le document de spécification détaillé du logiciel **Silogic** :

1. Calculez le **Point Fonction** : (a) le facteur de complexité technique (TFC) ; (b) le nombre de fonctions non ajusté (UFC).
2. Calculez les **métriques de Bang** (fonctions, données) de ce système.
