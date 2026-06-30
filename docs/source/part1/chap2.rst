.. _part1_chap2:

***********************************************************************
Chapitre 2 : La norme ISO/IEC 9126
***********************************************************************

La norme **ISO/IEC 9126** définit la qualité d'un logiciel à travers **6 critères
de base**, chacun décliné en **sous-critères**. C'est le vocabulaire commun qui
permet d'évaluer la qualité de façon objective.

Objectifs
=========

À la fin de ce chapitre, vous devez pouvoir :

- Énumérer les 6 critères de la norme ISO/IEC 9126 et leurs sous-critères
- Définir chaque critère et l'illustrer par un exemple
- Évaluer une application existante critère par critère


Les 6 critères de base
======================

- Capacité fonctionnelle
- Fiabilité
- Facilité d'utilisation
- Rendement
- Maintenabilité
- Portabilité

.. list-table::
   :header-rows: 1
   :widths: 16 30 30 24

   * - Critère
     - Définition
     - Sous-critères
     - Exemple
   * - **Capacité fonctionnelle**
     - Satisfaire les besoins exprimés par le client (les spécifications)
     - Aptitude (présence/adéquation des fonctionnalités), Exactitude (juste/correct), Interopérabilité (1), Sécurité
     - Vérifier et s'assurer des différentes fonctionnalités de l'application
   * - **Fiabilité**
     - Maintenir un niveau de service dans des conditions et une période données
     - Maturité, Tolérance aux fautes (2), Possibilité de récupération après panne
     - Fréquence de bugs ; comportement sans Internet ; version auto-enregistrée après coupure
   * - **Facilité d'utilisation**
     - L'effort à la prise en main du logiciel
     - Apprentissage (courbe), Compréhension (usage sans documentation), Exploitation
     - Combien de temps pour apprendre ? Peut-on écrire dans Word sans formation ?
   * - **Rendement**
     - Efficacité dans l'utilisation des ressources et effort de déploiement
     - Rapidité (temps), Utilisation des ressources (mémoire)
     - L'application est-elle rapide ? Facile à déployer ?
   * - **Maintenabilité**
     - Effort nécessaire pour faire évoluer le logiciel
     - Facilité d'analyse, Facilité de modification, Stabilité, **Testabilité**
     - Un code en un seul bloc est intestable ; découpé en fonctions, il est testable
   * - **Portabilité**
     - Capacité/effort pour transférer le logiciel d'une plateforme à une autre
     - Facilité d'installation, Interchangeabilité, Conformité (3)
     - Un ``.docx`` créé par Word s'ouvre dans Google Docs ou OpenOffice

(1) L'interopérabilité peut être ignorée si elle n'est pas une préoccupation pour votre logiciel.

(2) **Tolérance aux fautes** (que faire pendant la panne ?) vs **récupération après panne** (que faire après ?).

(3) La conformité renvoie aux normes liées à la portabilité.


Exemple complet : Microsoft Word
=================================

Évaluer une application revient à parcourir chaque sous-critère et à **justifier**.

.. list-table::
   :header-rows: 1
   :widths: 22 22 14 42

   * - Critère
     - Sous-critère
     - Réponse
     - Justification / exemple
   * - Capacité fonctionnelle
     - Aptitude
     - Oui
     - Capacité d'écrire du texte
   * -
     - Exactitude
     - Oui
     - « Mettre en gras » → le texte est bien en gras
   * -
     - Interopérabilité
     - Oui
     - On peut charger une feuille Excel dans Word
   * -
     - Sécurité
     - ??
     -
   * - Fiabilité
     - Maturité
     - Oui
     - Très peu de bugs, voire aucun
   * -
     - Tolérance aux fautes
     - Oui/Non
     - On arrive souvent à continuer après certaines erreurs
   * -
     - Récupération après panne
     - Oui
     - Version auto-enregistrée après coupure
   * - Facilité d'utilisation
     - Apprentissage
     - Oui/Non
     - On démarre vite, mais tout maîtriser prend du temps
   * -
     - Compréhension
     - Oui
     - Icônes intuitives (copier/coller/couper)
   * -
     - Exploitation
     - Oui
     - Word est abordable
   * - Maintenabilité
     - Facilité d'analyse / modification
     - Oui
     - Vu la cadence des nouvelles versions
   * -
     - Stabilité
     - Oui
     - Quasi-absence de bugs au quotidien
   * -
     - Testabilité
     - ??
     - On n'a jamais vu le code
   * - Portabilité
     - Facilité d'installation
     - Oui/Non
     - Oui sur un bon PC ; non car lourd (> 1 Go)
   * -
     - Interchangeabilité
     - Oui
     - ``.docx`` s'ouvre dans Google Docs
   * -
     - Conformité
     - Oui/Non
     - Installable sur de nombreuses plateformes, mais conformité aux normes non vérifiable

.. tip::
   Une réponse « ?? » est légitime : elle signale qu'on **ne peut pas conclure**
   sans information supplémentaire (ex. accès au code pour juger la testabilité).


Exercices
=========

.. note::
   Cet exercice prépare le **tableau d'évaluation individuel** (25 % de la note).

1. Choisissez une application que vous utilisez (navigateur, messagerie, jeu, …) et construisez son **tableau d'évaluation ISO/IEC 9126** complet (critère, sous-critère, réponse, justification).
2. Identifiez les **forces** et **faiblesses** de l'application à partir de votre tableau.
3. Pour deux sous-critères que vous avez notés « ?? », expliquez quelle information vous manque pour conclure.
