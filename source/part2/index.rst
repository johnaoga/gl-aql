.. _part2:


*************************************************************************************************
Chapitre 2 | Évaluation pratique de la qualité d'applications
*************************************************************************************************

Objectifs
=========

À l'issue de ce module, chaque étudiant.e sera capable de :

* Définir précisément chaque critère et sous-critère de la norme ISO/IEC 9126
* Identifier et donner des exemples concrets pour chaque (sous-)critère dans les logiciels du quotidien
* Analyser un logiciel existant en appliquant systématiquement les critères de qualité
* Construire un tableau d'évaluation complet selon la norme ISO/IEC 9126
* Justifier l'évaluation de qualité par des arguments techniques pertinents


Note de théorique
=======================================

Rappel des 6 critères de la norme ISO/IEC 9126
"""""""""""""""""""""""""""""""""""""""""""""""

La norme ISO/IEC 9126 définit **6 critères de qualité logicielle**, chacun composé de plusieurs sous-critères :


1. Capacité fonctionnelle
^^^^^^^^^^^^^^^^^^^^^^^^^^

**Définition :** Attributs du logiciel relatifs à sa capacité à satisfaire les besoins exprimés par le client (spécifications).

**Sous-critères :**

* **Aptitude** : Présence et adéquation des fonctionnalités requises
  
  * *Exemple* : Dans WhatsApp, la fonctionnalité d'envoi de messages est présente et répond au besoin principal

* **Exactitude** : Les résultats produits sont justes et corrects
  
  * *Exemple* : Quand j'envoie un message à quelqu'un via WhatsApp, il reçoit exactement le message envoyé

* **Interopérabilité** : Capacité d'interaction avec d'autres applications
  
  * *Exemple* : WhatsApp fait des backups sur Google Drive ; utilisation d'API de paiement sur un site d'e-commerce
  * *Note* : Ne pas considérer ce critère si l'interopérabilité ne concerne pas votre logiciel

* **Sécurité** : Respect des contraintes de sécurité (par exemple respect des propriétés ACID)
  
  * *Exemple* : Authentification obligatoire pour accéder au logiciel
  * *Note* : Il existe des normes spécifiques pour la sécurité (ISO/IEC 27001)


2. Fiabilité
^^^^^^^^^^^^

**Définition :** Capacité du logiciel à inspirer la confiance et à maintenir un certain niveau de service selon des conditions données.

**Sous-critères :**

* **Maturité** : Capacité à s'exécuter correctement généralement (idéalement tout le temps)
  
  * *Mesure* : Fréquence des bugs rencontrés

* **Tolérance aux fautes** : Capacité à maintenir un certain niveau de service même en présence de pannes
  
  * *Exemple* : Google Docs peut continuer à fonctionner en mode hors ligne dès que vous perdez la connexion

* **Récupération après sinistre** : Capacité à reprendre le service après une panne ou un incident
  
  * *Exemple* : Word propose de récupérer votre document après un arrêt inopiné de l'ordinateur (auto-saving)


3. Utilisabilité
^^^^^^^^^^^^^^^^

**Définition :** Effort nécessaire à la prise en main du logiciel par l'utilisateur.

**Sous-critères :**

* **Apprentissage** : Facilité et rapidité d'apprentissage du logiciel
  
  * *Questions à se poser* : En combien de temps peut-on apprendre ce logiciel ? Est-ce que le logiciel est facile à apprendre ?

* **Compréhension** : Capacité à utiliser l'application sans documentation
  
  * *Exemple* : La plupart d'entre nous avons commencé avec Word sans documentation ni formation
  * *Exemple* : Dans Google Meet, les icônes et les tooltips sont largement suffisants pour guider l'utilisateur

* **Exploitation** : Facilité d'utilisation au quotidien


4. Efficacité
^^^^^^^^^^^^^

**Définition :** Efficacité dans l'utilisation des ressources système.

**Sous-critères :**

* **Rapidité** : Performance en temps (complexité temporelle)
  
  * *Évaluation* : Le logiciel est-il lent ou rapide ? Quelle est sa complexité algorithmique ?
  * *Exemple critique* : Un algorithme de complexité exponentielle pour une tâche courante

* **Utilisation des ressources** : Utilisation optimale des ressources (mémoire, batterie, CPU, etc.)
  
  * *Exemples de problèmes* : Consomme trop de batterie, remplit la mémoire, utilisation excessive du CPU


5. Maintenabilité
^^^^^^^^^^^^^^^^^

**Définition :** Effort nécessaire pour faire évoluer le logiciel.

**Sous-critères :**

* **Facilité d'analyse** : Capacité à diagnostiquer facilement les problèmes
  
  * *Exemple* : Le logiciel dispose de logs informatifs, de messages d'erreurs clairs ou de numéros de référence de bugs

* **Facilité de modification** : Capacité à mettre à jour ou upgrader le logiciel
  
  * *Contre-exemple* : Code en un bloc, dupliqué, sans commentaires, sans fonctions, pas de modules, pas de classes, pas d'architecture
  * *Bon exemple* : Code propre, bien commenté, testé, programmation défensive, POO, architecture en couches

* **Testabilité** : Capacité du logiciel à se faire tester
  
  * *Principes* : Une fonction = une tâche simple, pas de duplication de code, découplage

* **Stabilité** : Risque d'effets secondaires après modifications
  
  * *Évaluation* : Présence de "code smells" (mauvaises pratiques de programmation)


6. Portabilité
^^^^^^^^^^^^^^

**Définition :** Effort nécessaire pour transférer le logiciel d'une plateforme à une autre.

**Sous-critères :**

* **Facilité d'installation** : Effort requis pour le déploiement
  
  * *Évaluation* : Le déploiement est-il simple ? Combien d'étapes sont nécessaires ?

* **Interchangeabilité** : Capacité à remplacer un logiciel par un autre
  
  * *Exemple* : Un document .docx peut être ouvert avec Microsoft Word, Google Docs, LibreOffice
  * *Notion importante* : Rétrocompatibilité

* **Conformité/Adaptabilité** : Respect des normes de portabilité
  
  * *Exemple* : Le logiciel s'exécute sur plusieurs plateformes ou systèmes d'exploitation (Windows, macOS, Linux)


Processus d'évaluation de la qualité
"""""""""""""""""""""""""""""""""""""

Pour évaluer la qualité d'un logiciel, suivez ces étapes :

1. **Identifier le logiciel** à évaluer et son contexte d'utilisation
2. **Parcourir systématiquement** chaque critère et sous-critère de la norme ISO/IEC 9126
3. **Donner des exemples concrets** tirés du logiciel pour chaque sous-critère applicable
4. **Justifier votre évaluation** avec des arguments techniques
5. **Synthétiser** dans un tableau récapitulatif
6. **Identifier les points forts** et **axes d'amélioration**


Construction d'un tableau d'évaluation
"""""""""""""""""""""""""""""""""""""""

Votre tableau d'évaluation doit contenir :

* **Critère** : Le critère principal (ex: Capacité fonctionnelle)
* **Sous-critère** : Le sous-critère spécifique (ex: Aptitude)
* **Définition** : Définition claire du sous-critère
* **Exemple** : Exemple concret tiré du logiciel évalué
* **Commentaire/Justification** : Votre analyse critique


À lire / Aller plus loin
=======================================

Slides du cours :


Livres de référence :


Aller plus loin :


Exercices théoriques
=======================================

.. note::
   Vous devez faire ces exercices avant la prochaine séance.

Exercice 1
""""""""""""

Choisissez un logiciel que vous utilisez quotidiennement (application mobile, logiciel de bureautique, site web, etc.) et :

1. Construisez un tableau d'évaluation complet selon la norme ISO/IEC 9126
2. Pour chaque sous-critère, donnez au moins un exemple concret tiré du logiciel
3. Justifiez votre évaluation avec des arguments techniques précis
4. Identifiez 3 points forts et 3 axes d'amélioration


Exercice 2
""""""""""""

Comparez deux logiciels similaires (ex: WhatsApp vs Telegram, Word vs Google Docs) :

1. Évaluez les deux logiciels selon les 6 critères de qualité
2. Identifiez les différences majeures en termes de qualité
3. Lequel répond le mieux aux critères de la norme ISO/IEC 9126 ? Justifiez


Exercice 3
""""""""""""

Pour chacun des scénarios suivants, identifiez quel(s) critère(s) et sous-critère(s) de qualité sont concernés :

1. Une application bancaire mobile demande une authentification biométrique
2. Un éditeur de texte sauvegarde automatiquement toutes les 30 secondes
3. Une application de messagerie consomme 50% de la batterie en 2 heures
4. Un logiciel de comptabilité ne peut pas importer de fichiers Excel
5. Un jeu vidéo plante systématiquement après 1 heure de jeu
6. Une application nécessite 3 jours de formation pour être utilisée correctement
7. Un site web fonctionne uniquement sur Chrome et pas sur Firefox
8. Le code source d'une application contient des fonctions de 500 lignes sans commentaires


Exercice 4
""""""""""""

Réflexion critique :

1. Est-il possible qu'un logiciel soit excellent sur certains critères et mauvais sur d'autres ? Donnez un exemple
2. Selon vous, quel est le critère le plus important ? Justifiez votre réponse
3. Comment la norme ISO/IEC 9126 peut-elle aider dans le développement de nouveaux logiciels ?