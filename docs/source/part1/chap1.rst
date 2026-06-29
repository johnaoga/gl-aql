.. _part1_chap1:

***********************************************************************
Chapitre 1 : Introduction à l'AQL
***********************************************************************

**AQL = Assurance et Qualité du Logiciel.** Ce chapitre introduit les deux faces
du cours — **assurabilité** et **testabilité** — et explique pourquoi la qualité,
intrinsèquement **subjective**, doit s'appuyer sur une **norme**.

Objectifs
=========

À la fin de ce chapitre, vous devez pouvoir :

- Définir l'**assurabilité** et la **testabilité** et les distinguer
- Expliquer en quoi la qualité est subjective
- Justifier le recours à une **norme** pour objectiver la qualité


Assurabilité et testabilité
===========================

Le cours articule deux aspects complémentaires :

- **Assurabilité** — la capacité à **s'assurer** qu'un logiciel est de qualité :
  agir *en amont* (spécification, conception, code) et évaluer le produit selon des
  critères. C'est une démarche de **garantie** de la qualité.
- **Testabilité** — la capacité d'un logiciel à **se faire tester** : concevoir et
  exécuter des tests qui vérifient son comportement. C'est l'un des sous-critères de
  la maintenabilité (voir :doc:`ISO/IEC 9126 <chap2>`), et un aspect évalué à part
  entière dans le :doc:`projet <../part3/index>`.

.. note::
   Dans le projet, ces deux aspects sont évalués séparément et **en croisé** : un
   groupe assure la qualité de son logiciel (assurabilité), un autre groupe en
   conçoit les tests (testabilité).


La subjectivité de la qualité → la norme
========================================

Dire « mon logiciel est performant » ou « mon logiciel est fiable » ne veut pas
dire grand-chose tant qu'on ne précise pas **ce que cela signifie** et **comment on
le vérifie**. Deux personnes peuvent employer les mêmes mots pour des réalités
différentes.

Pour sortir de cette **subjectivité**, on a besoin :

1. d'un **vocabulaire commun** et de **critères explicites** → c'est le rôle d'une
   **norme** (ici :doc:`ISO/IEC 9126 <chap2>`) ;
2. d'un moyen de **quantifier** ces critères → c'est le rôle des **mesures** et des
   :doc:`métriques <../part2/index>`.

.. admonition:: Fil directeur du cours
   :class: important

   **Norme** (définir la qualité) → **mesures/métriques** (la quantifier) →
   **assurabilité & testabilité** (la garantir et la vérifier sur un projet).


Exercice
========

Reformulez les affirmations suivantes en critères **vérifiables** : (a) « le
logiciel est rapide » ; (b) « le logiciel est facile à utiliser » ; (c) « le
logiciel est fiable ». Pour chacune, proposez une façon concrète de la mesurer.
