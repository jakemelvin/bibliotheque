# Gestion d'une Bibliothèque

## Description du Projet

Cette application Java a pour objectif de gérer une bibliothèque en permettant de suivre les livres, les membres, et les emprunts.

## Instructions pour Lancer le Projet

### Prérequis

1. **JDK installé** : Assurez-vous que Java Development Kit (JDK) est installé sur votre machine (version 11 ou supérieure).
2. **PostgreSQL installé** : Installez PostgreSQL et configurez une base de données.
3. **IDE** : Utilisez un IDE comme IntelliJ IDEA, Eclipse ou VS Code avec des extensions Java.
4. **Driver JDBC PostgreSQL** : Téléchargez et ajoutez le fichier JAR du driver PostgreSQL JDBC dans le classpath de votre projet.

### Étape 1 : Cloner le Repository

Clonez le repository GitHub contenant le code source du projet :

```bash
git clone <lien_du_repository>
cd gestion-bibliotheque
```

### Étape 2 : Configurer la Base de Données

1. Connectez-vous à PostgreSQL et créez une base de données pour le projet :
   ```sql
   CREATE DATABASE gestion_bibliotheque;
   ```

2. Exécutez le script SQL fourni dans `resources/schema.sql` pour créer les tables nécessaires :
   ```bash
   psql -U <votre_utilisateur> -d gestion_bibliotheque -f resources/schema.sql
   ```

3. Mettez à jour les paramètres de connexion à la base de données dans la classe `DatabaseConnection.java` :
   ```java
   private static final String URL = "jdbc:postgresql://localhost:5432/gestion_bibliotheque";
   private static final String USER = "votre_utilisateur";
   private static final String PASSWORD = "votre_mot_de_passe";
   ```

### Étape 3 : Compiler et Exécuter le Projet

1. **Compilation** : Compilez le projet depuis votre IDE ou en ligne de commande :
   ```bash
   javac -d bin src/**/*.java
   ```

2. **Exécution** : Lancez le programme principal :
   ```bash
   java -cp bin Main
   ```

### Étape 4 : Utiliser l'Application

1. Naviguez dans le menu interactif :
   ```
   1. Ajouter un livre
   2. Rechercher un livre
   3. Inscrire un membre
   4. Enregistrer un emprunt
   5. Retourner un livre
   6. Quitter
   ```
2. Suivez les instructions à l’écran pour gérer les livres, membres et emprunts.

### Étape 5 : Tester les Fonctionnalités

- Vérifiez que toutes les fonctionnalités (ajout, suppression, recherche, gestion des retards, etc.) fonctionnent correctement.
- Consultez la base de données pour confirmer que les modifications y sont bien reflétées.

## Structure du Projet

```plaintext
├── src
│   ├── Main.java
│   ├── Livre.java
│   ├── Membre.java
│   ├── Emprunt.java
│   └── dao
│       ├── LivreDAO.java
│       ├── MembreDAO.java
│       └── EmpruntDAO.java
├── resources
│   └── schema.sql
├── classes_UML.pdf
├── lien_github.txt
└── README.md
```