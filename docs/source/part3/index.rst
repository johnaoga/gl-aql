.. _part3:


*************************************************************************************************
Chapitre 3 | Métriques logicielles
*************************************************************************************************

Objectifs
=========

À l'issue de ce module, chaque étudiant.e sera capable de :

* Expliquer et appliquer la complexité cyclomatique de McCabe et la complexité Big O
* Maîtriser les métriques de point fonction et les métriques de Bang (De Marco)
* Appliquer les métriques orientées objet (Chidamber et Kamerer)
* Évaluer la cohésion et le couplage dans un système logiciel
* Relier les métriques aux différents critères de qualité ISO/IEC 9126
* Présenter et appliquer des métriques logicielles pour l'évaluation quantitative de la qualité


Note de théorique
=======================================

Introduction aux métriques logicielles
"""""""""""""""""""""""""""""""""""""""

Les **métriques logicielles** sont des mesures quantitatives permettant d'évaluer différents aspects de la qualité d'un logiciel. Contrairement à l'évaluation qualitative basée sur les critères ISO/IEC 9126, les métriques fournissent des valeurs numériques objectives qui aident à :

* Mesurer la complexité du code
* Évaluer la maintenabilité d'un système
* Comparer différentes solutions techniques
* Identifier les zones à risque dans le code
* Suivre l'évolution de la qualité au fil du temps


1. Complexité cyclomatique de McCabe
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Définition :** La complexité cyclomatique mesure le nombre de chemins d'exécution indépendants dans un programme.

**Formule :** 

.. math::

   V(G) = E - N + 2P

Où :

* E = nombre d'arêtes du graphe de contrôle
* N = nombre de nœuds
* P = nombre de composantes connexes (généralement P = 1)

**Formule simplifiée :**

.. math::

   V(G) = \text{nombre de décisions} + 1

Les décisions incluent : ``if``, ``while``, ``for``, ``case``, ``catch``, ``&&``, ``||``, ``?``

**Interprétation :**

* **1-10** : Code simple, faible risque
* **11-20** : Code modérément complexe, risque modéré
* **21-50** : Code complexe, risque élevé
* **> 50** : Code très complexe, non testable, à refactoriser

**Exemple :**

.. code-block:: java

    public int calculerRemise(int age, boolean etudiant, double montant) {
        if (age < 18) {                    // +1
            return 20;
        } else if (age >= 65) {            // +1
            return 15;
        } else if (etudiant) {             // +1
            return 10;
        }
        return 0;
    }
    // Complexité cyclomatique = 3 + 1 = 4

**Lien avec ISO/IEC 9126 :**

* **Maintenabilité** : Plus la complexité est élevée, plus le code est difficile à maintenir
* **Testabilité** : Une complexité élevée nécessite plus de tests
* **Fiabilité** : Code complexe = plus de risques de bugs


2. Notation Big O (Complexité algorithmique)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Définition :** La notation Big O mesure la complexité temporelle ou spatiale d'un algorithme en fonction de la taille de l'entrée.

**Notations courantes :**

* :math:`O(1)` - **Constant** : Temps d'exécution indépendant de la taille
* :math:`O(\log n)` - **Logarithmique** : Division par 2 à chaque étape (recherche binaire)
* :math:`O(n)` - **Linéaire** : Parcours simple d'une structure
* :math:`O(n \log n)` - **Linéarithmique** : Algorithmes de tri efficaces (merge sort, quick sort)
* :math:`O(n^2)` - **Quadratique** : Boucles imbriquées
* :math:`O(2^n)` - **Exponentielle** : Algorithmes récursifs non optimisés
* :math:`O(n!)` - **Factorielle** : Permutations, problèmes combinatoires

**Autres notations :**

* :math:`\Omega` (Omega) : Borne inférieure (meilleur cas)
* :math:`\Theta` (Theta) : Borne exacte (cas moyen)
* :math:`\sim` (Tilde) : Approximation précise du nombre d'opérations

**Exemple :**

.. code-block:: java

    // O(1) - Temps constant
    public int getElement(int[] array, int index) {
        return array[index];
    }

    // O(n) - Temps linéaire
    public int sum(int[] array) {
        int total = 0;
        for (int value : array) {
            total += value;
        }
        return total;
    }

    // O(n²) - Temps quadratique
    public void bubbleSort(int[] array) {
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array.length - 1; j++) {
                if (array[j] > array[j + 1]) {
                    // swap
                }
            }
        }
    }

**Lien avec ISO/IEC 9126 :**

* **Efficacité** : Directement lié à la performance temporelle
* **Utilisabilité** : Un algorithme inefficace ralentit l'expérience utilisateur


3. Métriques de point fonction (Function Points)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Définition :** Les points de fonction mesurent la taille fonctionnelle d'un logiciel du point de vue de l'utilisateur.

**Éléments mesurés :**

* **Entrées externes** (EI) : Données entrées par l'utilisateur
* **Sorties externes** (EO) : Données produites pour l'utilisateur
* **Interrogations externes** (EQ) : Requêtes simples
* **Fichiers internes** (ILF) : Données stockées et maintenues par l'application
* **Fichiers externes** (EIF) : Données référencées mais maintenues par d'autres applications

**Formule :**

.. math::

   FP = \sum (\text{nombre d'éléments} \times \text{poids de complexité})

**Utilité :**

* Estimation de l'effort de développement
* Comparaison de productivité entre projets
* Calcul du coût de développement


4. Métriques de Bang (De Marco)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Définition :** Les métriques de Bang mesurent la quantité de fonctionnalités livrées du point de vue de l'utilisateur.

**Composantes :**

* **Primitives fonctionnelles** : Nombre de transformations de données
* **Éléments de données** : Objets de données manipulés
* **Relations** : Connexions entre éléments de données

**Formule simplifiée :**

.. math::

   \text{Bang} = (\text{Primitives fonctionnelles})^{w1} \times (\text{Éléments de données})^{w2}

Où w1 et w2 sont des poids ajustables selon le projet.


5. Métriques orientées objet (Chidamber et Kemerer)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Suite de métriques CK :**

**WMC (Weighted Methods per Class) - Nombre pondéré de méthodes**

* Compte le nombre de méthodes dans une classe
* Plus élevé = classe plus complexe

**DIT (Depth of Inheritance Tree) - Profondeur de l'arbre d'héritage**

* Mesure la profondeur maximale de la hiérarchie d'héritage
* **Valeurs recommandées** : 0-5
* Trop élevé = complexité accrue, réutilisabilité compromise

**NOC (Number of Children) - Nombre d'enfants**

* Nombre de sous-classes directes
* Indique le niveau de réutilisation

**CBO (Coupling Between Objects) - Couplage entre objets**

* Nombre de classes auxquelles une classe est couplée
* **Valeurs recommandées** : 0-5
* Plus élevé = moins de modularité

**RFC (Response For a Class) - Ensemble de réponses d'une classe**

* Nombre de méthodes pouvant être invoquées en réponse à un message
* Mesure la complexité potentielle

**LCOM (Lack of Cohesion of Methods) - Manque de cohésion**

* Mesure si les méthodes d'une classe travaillent ensemble
* Faible LCOM = bonne cohésion

**Exemple d'application :**

.. code-block:: java

    // Classe avec bon CBO (faible couplage)
    public class Calculator {
        public int add(int a, int b) {
            return a + b;
        }
    }

    // Classe avec mauvais CBO (fort couplage)
    public class OrderProcessor {
        private Database db;              // Couplage 1
        private EmailService email;       // Couplage 2
        private PaymentGateway payment;   // Couplage 3
        private InventorySystem inventory; // Couplage 4
        private Logger logger;            // Couplage 5
        private NotificationService notif; // Couplage 6
        // CBO = 6 (trop élevé)
    }


6. Cohésion et Couplage
^^^^^^^^^^^^^^^^^^^^^^^^

**Cohésion**

**Définition :** Degré auquel les éléments d'un module sont liés entre eux.

**Types de cohésion (du meilleur au pire) :**

* **Cohésion fonctionnelle** : Toutes les parties contribuent à une seule tâche bien définie
* **Cohésion séquentielle** : Les sorties d'une partie sont les entrées d'une autre
* **Cohésion de communication** : Les parties travaillent sur les mêmes données
* **Cohésion procédurale** : Les parties suivent une séquence d'exécution
* **Cohésion temporelle** : Les parties sont exécutées au même moment
* **Cohésion logique** : Les parties sont regroupées car elles sont similaires
* **Cohésion coïncidente** : Aucune relation significative (à éviter)

**Exemple de bonne cohésion :**

.. code-block:: java

    // Classe avec forte cohésion fonctionnelle
    public class EmailValidator {
        public boolean isValid(String email) {
            return hasAtSymbol(email) && 
                   hasDomain(email) && 
                   isValidFormat(email);
        }
        
        private boolean hasAtSymbol(String email) { /* ... */ }
        private boolean hasDomain(String email) { /* ... */ }
        private boolean isValidFormat(String email) { /* ... */ }
    }


**Couplage**

**Définition :** Degré d'interdépendance entre les modules.

**Types de couplage (du meilleur au pire) :**

* **Pas de couplage** : Modules indépendants
* **Couplage par données** : Modules partagent des données simples
* **Couplage par structure** : Modules partagent des structures de données complexes
* **Couplage par contrôle** : Un module contrôle le flux d'un autre
* **Couplage externe** : Modules dépendent d'éléments externes
* **Couplage par contenu** : Un module modifie directement un autre (à éviter)

**Exemple de faible couplage (bon) :**

.. code-block:: java

    // Interface pour découpler
    public interface PaymentProcessor {
        boolean processPayment(double amount);
    }

    public class OrderService {
        private PaymentProcessor paymentProcessor;
        
        public OrderService(PaymentProcessor processor) {
            this.paymentProcessor = processor;
        }
    }


**Principe général :**

* **Haute cohésion** = bon design
* **Faible couplage** = bon design


Relation entre métriques et critères ISO/IEC 9126
""""""""""""""""""""""""""""""""""""""""""""""""""

+------------------------------+--------------------------------------------------+
| **Métrique**                 | **Critères ISO/IEC 9126 concernés**             |
+==============================+==================================================+
| Complexité cyclomatique      | Maintenabilité, Testabilité, Fiabilité          |
+------------------------------+--------------------------------------------------+
| Complexité Big O             | Efficacité (rapidité)                            |
+------------------------------+--------------------------------------------------+
| Points de fonction           | Capacité fonctionnelle                           |
+------------------------------+--------------------------------------------------+
| Métriques CK (CBO, LCOM)     | Maintenabilité, Réutilisabilité                  |
+------------------------------+--------------------------------------------------+
| Cohésion                     | Maintenabilité, Testabilité                      |
+------------------------------+--------------------------------------------------+
| Couplage                     | Maintenabilité, Portabilité, Réutilisabilité     |
+------------------------------+--------------------------------------------------+


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
""""""""""

Calculez la complexité cyclomatique des fonctions Java suivantes :

.. code-block:: java

    // Fonction 1
    public boolean isEligible(int age, boolean hasLicense, int experience) {
        if (age >= 18 && hasLicense) {
            if (experience > 2) {
                return true;
            }
        }
        return false;
    }

    // Fonction 2
    public String getGrade(int score) {
        if (score >= 90) {
            return "A";
        } else if (score >= 80) {
            return "B";
        } else if (score >= 70) {
            return "C";
        } else if (score >= 60) {
            return "D";
        } else {
            return "F";
        }
    }

    // Fonction 3
    public int fibonacci(int n) {
        if (n <= 1) {
            return n;
        }
        return fibonacci(n - 1) + fibonacci(n - 2);
    }


Exercice 2
""""""""""

Déterminez la complexité Big O des algorithmes suivants et justifiez votre réponse :

.. code-block:: java

    // Algorithme 1
    public void printPairs(int[] array) {
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array.length; j++) {
                System.out.println(array[i] + "," + array[j]);
            }
        }
    }

    // Algorithme 2
    public int binarySearch(int[] sortedArray, int target) {
        int left = 0;
        int right = sortedArray.length - 1;
        
        while (left <= right) {
            int mid = (left + right) / 2;
            if (sortedArray[mid] == target) return mid;
            if (sortedArray[mid] < target) left = mid + 1;
            else right = mid - 1;
        }
        return -1;
    }

    // Algorithme 3
    public void printUnorderedPairs(int[] array) {
        for (int i = 0; i < array.length; i++) {
            for (int j = i + 1; j < array.length; j++) {
                System.out.println(array[i] + "," + array[j]);
            }
        }
    }


Exercice 3
""""""""""

Analysez la classe Java suivante et calculez :

1. Le nombre de méthodes (WMC)
2. Le couplage (CBO) 
3. Proposez des améliorations pour réduire le couplage

.. code-block:: java

    public class UserService {
        private DatabaseConnection db;
        private EmailSender emailSender;
        private Logger logger;
        private PasswordHasher hasher;
        private SessionManager sessionManager;
        
        public void registerUser(String username, String password, String email) {
            logger.log("Registering user: " + username);
            String hashedPassword = hasher.hash(password);
            db.insert("users", username, hashedPassword, email);
            emailSender.sendWelcomeEmail(email);
            sessionManager.createSession(username);
        }
        
        public boolean loginUser(String username, String password) {
            logger.log("Login attempt: " + username);
            String hashedPassword = hasher.hash(password);
            boolean valid = db.validateCredentials(username, hashedPassword);
            if (valid) {
                sessionManager.createSession(username);
            }
            return valid;
        }
        
        public void deleteUser(String username) {
            logger.log("Deleting user: " + username);
            db.delete("users", username);
            sessionManager.invalidateSession(username);
        }
    }



Exercice 4
""""""""""

Réflexion critique : Établissez les liens entre les métriques et les critères ISO/IEC 9126

1. Expliquez comment la complexité cyclomatique impacte la maintenabilité
2. En quoi une complexité Big O élevée affecte-t-elle l'efficacité et l'utilisabilité ?
3. Comment un couplage élevé compromet-il la portabilité et la maintenabilité ?
4. Pourquoi une faible cohésion nuit-elle à la testabilité ?
5. Proposez des seuils acceptables pour chaque métrique dans un projet professionnel