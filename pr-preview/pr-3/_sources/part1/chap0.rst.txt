.. _part1_chap0:

***********************************************************************
Chapitre 0 : Introduction à la qualité d'un logiciel
***********************************************************************

Avant de parler d'*assurance* et de *mesure* de la qualité, posons la question de
fond : **qu'est-ce que la qualité d'un logiciel ?**

Objectifs
=========

À la fin de ce chapitre, vous devez pouvoir :

- Distinguer un **bon logiciel** d'un **logiciel de qualité**
- Citer des critères de qualité d'un logiciel
- Comprendre pourquoi la qualité doit être **définie** et **mesurée**, et non simplement ressentie


Exercice introductif
====================

1. Pour vous, qu'est-ce qu'un logiciel « de qualité » ? Donnez trois exemples de logiciels que vous jugez de qualité, et dites pourquoi.
2. Deux personnes affirment que leur logiciel est « performant ». Disent-elles forcément la même chose ?
3. Un logiciel sans bug est-il forcément de qualité ? Un logiciel de qualité est-il forcément sans bug ?


Bon logiciel vs logiciel de qualité
===================================

Il est utile de distinguer deux notions proches.

- **Bon logiciel** — un logiciel qui *fait ce qu'on attend de lui* : il respecte le
  cahier des charges et fonctionne (correct, complet, suffisamment efficace).
- **Logiciel de qualité** — un logiciel qui respecte des **critères de qualité bien
  définis** : fonctionnalité, fiabilité, facilité d'utilisation, rendement,
  maintenabilité, portabilité (ce sont précisément les critères de la norme
  :doc:`ISO/IEC 9126 <chap2>`).

.. note::
   Un logiciel peut « marcher » (bon logiciel) sans être *de qualité* : par exemple
   un code qui fonctionne mais impossible à maintenir, à tester ou à porter sur une
   autre plateforme. La **qualité** englobe et dépasse le simple bon fonctionnement.

.. admonition:: À retenir
   :class: important

   Évaluer la qualité, c'est confronter un logiciel à un ensemble de **critères
   explicites** — pas à une impression. Tout l'enjeu du cours est de rendre ces
   critères **objectifs** et **mesurables**.


Exercice
========

Reprenez les trois logiciels de l'exercice introductif. Pour chacun, dites s'il
est selon vous un « bon logiciel », un « logiciel de qualité », ou les deux —
et justifiez à l'aide d'au moins deux critères.
