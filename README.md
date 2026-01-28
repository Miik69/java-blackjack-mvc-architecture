# java-blackjack-mvc-architecture
Implémentation complète du Blackjack en Java (Swing) reposant sur une architecture MVC stricte et l'utilisation de multiples Design Patterns (Command, Decorator, Strategy, Observer, Factory).
# ♠️ Blackjack - Architecture Logicielle & Design Patterns

Ce projet est une implémentation robuste du jeu de Blackjack en **Java**, réalisée dans le cadre d'un module de conception logicielle. 

L'objectif n'était pas seulement de créer un jeu fonctionnel, mais de concevoir une **architecture modulaire, extensible et maintenable** en appliquant les principes de la Programmation Orientée Objet (POO).

## 🚀 Fonctionnalités
* **Mode Graphique :** Interface complète réalisée avec **Java Swing**.
* **Adversaires IA :** Intégration de joueurs contrôlés par l'ordinateur ("Bots") avec des stratégies interchangeables.
* **Règles Complètes :** Gestion du *Hit*, *Stay*, *Double*, *Split* (séparation de main) et *Assurance*.
* **Multijoueur local :** Gestion de plusieurs mains et joueurs en simultané.

## 🏗️ Architecture Technique

Le projet respecte scrupuleusement le pattern **MVC (Modèle-Vue-Contrôleur)** pour séparer la logique métier de l'interface utilisateur.

### Design Patterns utilisés
Ce projet est une démonstration pratique de plusieurs patrons de conception majeurs :

1.  **Observer Pattern :** Pour la liaison Modèle-Vue. Les vues (`VueJoueur`, `VueCartes`) écoutent les changements d'état des modèles (`Paquet`, `Joueur`) pour se mettre à jour automatiquement sans couplage fort.
2.  **Strategy Pattern :** Utilisé pour l'IA (`JoueurIA`). Cela permet de changer dynamiquement l'intelligence du bot (ex: `RandomStrategie`) sans modifier le code du joueur.
3.  **Decorator Pattern :** Pour gérer la complexité des mains. Une main de base (`MainBasic`) peut être "décorée" pour devenir une main assurée (`MainAssure`), splittée (`MainSplite`) ou doublée (`MainDouble`).
4.  **Command Pattern :** Chaque action de jeu (Tirer, Rester...) est encapsulée dans une classe propre implémentant l'interface `Coup`. Cela rend le contrôleur extensible (Open/Closed Principle).
5.  **Factory Pattern :** Via `PaquetFactory` pour centraliser et simplifier la création des paquets de cartes.
6.  **Adapter Pattern :** `ModeleSolde` adapte les objets `Joueur` pour qu'ils puissent être affichés nativement dans une `JTable` Swing.

## 🛠️ Stack Technique
* **Langage :** Java 
* **UI :** Swing
* **Build System :** Apache Ant
* **Tests :** JUnit 4

## 📦 Installation et Lancement

Le projet est divisé en deux modules : `cartes` (librairie) et `blackjack` (le jeu).

### Pré-requis
* JDK 8 ou supérieur
* Apache Ant

### Compilation
Il est nécessaire de compiler la librairie `cartes` avant le jeu.

1.  **Compiler la librairie :**
    ```bash
    cd cartes
    ant dist
    ```
    *(Cela génère le `.jar` et le copie automatiquement dans le dossier lib du blackjack)*

2.  **Lancer le jeu :**
    ```bash
    cd ../blackjack
    ant run
    ```
