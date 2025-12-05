.. _part4:




*************************************************************************************************
Chapitre 4 | Testabilité et Assurabilité dans les projets logiciels
*************************************************************************************************

Objectifs
=========

À l'issue de ce module, chaque étudiant.e sera capable de :

* Concevoir une architecture logicielle favorisant la testabilité
* Implémenter des stratégies de test appropriées (unitaires, intégration, système)
* Évaluer la testabilité d'un système développé par une autre équipe
* Appliquer les principes d'assurabilité dans le développement
* Documenter les processus de test et d'assurance qualité
* Évaluer objectivement un projet développé par une autre équipe
* Identifier les points d'amélioration et proposer des solutions concrètes


Note de théorique
=======================================

1. Introduction à la testabilité et l'assurabilité
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Testabilité** : Capacité d'un système logiciel à être testé efficacement. Un logiciel testable permet de détecter facilement les défauts et de vérifier que les exigences sont satisfaites.

**Assurabilité** : Capacité d'un système à démontrer qu'il répond aux critères de qualité définis. C'est la facilité avec laquelle on peut prouver la qualité d'un logiciel.

**Relation avec ISO/IEC 9126 :**

* **Testabilité** → Sous-critère de **Maintenabilité**
* **Assurabilité** → Englobe tous les critères de qualité (Fiabilité, Maintenabilité, Utilisabilité, etc.)


2. Stratégies de test
^^^^^^^^^^^^^^^^^^^^^^

**2.1. Tests unitaires**

**Définition :** Testent une unité isolée de code (une méthode, une classe) indépendamment du reste du système.

**2.2. Tests d'intégration**

**Définition :** Testent l'interaction entre plusieurs composants ou modules.

**2.3. Tests système (End-to-End)**

**Définition :** Testent le système complet dans un environnement proche de la production.


3. Outils et frameworks de test
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

*À compléter selon le contexte technologique*


4. Principes d'assurabilité
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**4.1. Documentation complète**

* Spécifications claires des exigences
* Documentation de l'architecture
* Commentaires dans le code
* Guide utilisateur

**4.2. Traçabilité**

Lien entre exigences → design → code → tests


**4.3. Processus de revue de code**

**Checklist de revue :**

* Le code suit-il les conventions de nommage ?
* Y a-t-il des duplications de code ?
* Les méthodes sont-elles trop longues ?
* Les dépendances sont-elles injectées ?
* Y a-t-il des tests pour ce code ?
* Le code est-il bien commenté ?
* Y a-t-il des problèmes de sécurité évidents ?


5. Évaluation de la testabilité d'un projet
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Grille d'évaluation de la testabilité :**

+----------------------------------+---------------+---------------+---------------+
| **Critère**                      | **Faible**    | **Moyen**     | **Élevé**     |
+==================================+===============+===============+===============+
| Couverture de tests              | < 50%         | 50-80%        | > 80%         |
+----------------------------------+---------------+---------------+---------------+
| Injection de dépendances         | Absente       | Partielle     | Complète      |
+----------------------------------+---------------+---------------+---------------+
| Complexité cyclomatique moyenne  | > 15          | 10-15         | < 10          |
+----------------------------------+---------------+---------------+---------------+
| Couplage (CBO moyen)             | > 10          | 5-10          | < 5           |
+----------------------------------+---------------+---------------+---------------+
| Taille des méthodes (lignes)     | > 50          | 20-50         | < 20          |
+----------------------------------+---------------+---------------+---------------+

**Questions à se poser lors de l'évaluation :**

1. Les tests sont-ils présents et pertinents ?
2. Peut-on tester chaque composant isolément ?
3. Y a-t-il des dépendances cachées (singletons, méthodes statiques) ?
4. Le code utilise-t-il l'injection de dépendances ?
5. Les méthodes sont-elles courtes et focalisées ?
6. Le couplage est-il faible entre les modules ?
7. Y a-t-il une documentation des tests ?


À lire / Aller plus loin
=======================================

Slides du cours :

Livres de référence :

Aller plus loin :


Exercices théoriques
=======================================

.. note::
    Ces exercices de fin de module constituent une évaluation sommative essentielle. Leur réalisation complète et approfondie est requise pour valider les compétences du module.



Exercice 1
""""""""""

Évaluez la testabilité du projet suivant selon la grille fournie dans le cours. Identifiez au moins 5 problèmes de testabilité et proposez des solutions.

**Structure du projet :**

.. code-block:: java

    public class BlogApplication {
        private static BlogApplication instance;
        private Connection dbConnection;
        
        private BlogApplication() {
            try {
                dbConnection = DriverManager.getConnection(
                    "jdbc:mysql://localhost/blog", "root", "password");
            } catch (SQLException e) {
                e.printStackTrace();
            }
        }
        
        public static BlogApplication getInstance() {
            if (instance == null) {
                instance = new BlogApplication();
            }
            return instance;
        }
        
        public void createPost(String title, String content, int authorId) {
            try {
                // Validation
                if (title.length() < 5 || title.length() > 200) {
                    System.out.println("Invalid title length");
                    return;
                }
                
                if (content.length() < 50) {
                    System.out.println("Content too short");
                    return;
                }
                
                // Vérifier l'auteur
                Statement stmt = dbConnection.createStatement();
                ResultSet rs = stmt.executeQuery(
                    "SELECT * FROM users WHERE id = " + authorId);
                
                if (!rs.next()) {
                    System.out.println("Author not found");
                    return;
                }
                
                String authorEmail = rs.getString("email");
                
                // Insérer le post
                stmt.execute("INSERT INTO posts (title, content, author_id, created_at) VALUES ('" 
                    + title + "', '" + content + "', " + authorId + ", NOW())");
                
                // Envoyer notification
                EmailUtil.send(authorEmail, "Post Created", 
                    "Your post '" + title + "' has been published");
                
                // Logger
                FileWriter writer = new FileWriter("blog.log", true);
                writer.write("[" + new Date() + "] Post created: " + title + "\n");
                writer.close();
                
                System.out.println("Post created successfully");
                
            } catch (Exception e) {
                e.printStackTrace();
            }
        }
        
        public List<Post> getAllPosts() {
            List<Post> posts = new ArrayList<>();
            try {
                Statement stmt = dbConnection.createStatement();
                ResultSet rs = stmt.executeQuery("SELECT * FROM posts ORDER BY created_at DESC");
                
                while (rs.next()) {
                    Post post = new Post();
                    post.setId(rs.getInt("id"));
                    post.setTitle(rs.getString("title"));
                    post.setContent(rs.getString("content"));
                    post.setAuthorId(rs.getInt("author_id"));
                    posts.add(post);
                }
            } catch (SQLException e) {
                e.printStackTrace();
            }
            return posts;
        }
    }


Exercice 2 - Projet pratique
""""""""""""""""""""""""""""""

**Développement d'un système testable**

Développez un système de gestion de bibliothèque avec les fonctionnalités suivantes :

* Ajouter/supprimer des livres
* Emprunter/retourner des livres
* Rechercher des livres
* Gérer les membres

**Contraintes :**

* Utiliser l'injection de dépendances
* Couverture de tests ≥ 80%
* Complexité cyclomatique < 10 par méthode
* Architecture en couches
* Documentation complète

**Livrables :**

1. Code source avec tests
2. Rapport de couverture de code
3. Documentation de l'architecture


Exercice 3 - Évaluation croisée
"""""""""""""""""""""""""""""""""

**Évaluation d'un projet tiers**

Vous recevrez le code d'un projet développé par une autre équipe. Votre mission est d'évaluer sa testabilité et son assurabilité.

**Tâches :**

1. **Analyse de la testabilité** :
   
   * Calculer la couverture de tests
   * Évaluer la complexité cyclomatique
   * Identifier les dépendances problématiques
   * Mesurer le couplage et la cohésion

2. **Analyse de l'assurabilité** :
   
   * Vérifier la présence de documentation
   * Évaluer la traçabilité exigences → tests
   * Analyser l'architecture
   * Vérifier les processus de revue de code

3. **Rapport d'évaluation** :
   
   * Tableau récapitulatif selon ISO/IEC 9126
   * Identification des 5 principaux problèmes
   * Propositions d'amélioration concrètes et priorisées
   * Recommandations pour augmenter la testabilité

4. **Présentation** :
   
   * Présenter vos retours  à l'équipe évaluée (10 min)
   * Discussion constructive sur les améliorations possibles

**Grille d'évaluation à utiliser :**

+----------------------------------+---------------+---------------+---------------+
| **Critère**                      | **Pts /5**    | **Observation** | **Priorité** |
+==================================+===============+===============+===============+
| Couverture de tests              |               |                 |              |
+----------------------------------+---------------+---------------+---------------+
| Architecture                     |               |                 |              |
+----------------------------------+---------------+---------------+---------------+
| Injection de dépendances         |               |                 |              |
+----------------------------------+---------------+---------------+---------------+
| Complexité du code               |               |                 |              |
+----------------------------------+---------------+---------------+---------------+
| Couplage et cohésion             |               |                 |              |
+----------------------------------+---------------+---------------+---------------+
| Documentation                    |               |                 |              |
+----------------------------------+---------------+---------------+---------------+
| Qualité des tests                |               |                 |              |
+----------------------------------+---------------+---------------+---------------+