# Projet Wator : Simulation de l'Écosystème Marin

Ce projet simule l'écosystème marin en modélisant les comportements des requins et des poissons dans une grille représentant l'océan. Le but est de comprendre les interactions entre prédateurs et proies et d'observer l'évolution d'une population dans un environnement dynamique.

## Table des Matières

1. [Contexte et Objectifs](#contexte-et-objectifs)
2. [Structure du Projet](#structure-du-projet)
3. [Fonctionnalités des Classes](#fonctionnalités-des-classes)
    - [Classe Fish](#classe-fish)
    - [Classe Shark](#classe-shark)
4. [Lancement de la Simulation](#lancement-de-la-simulation)
5. [Exemple d'Utilisation](#exemple-dutilisation)
6. [Aperçu des Résultats](#aperçu-des-résultats)

---

### Contexte et Objectifs

Le modèle Wator est une simulation inspirée de la théorie des automates cellulaires, où une grille représente l'océan, et chaque cellule peut contenir un poisson, un requin ou rester vide. Les objectifs principaux de ce projet sont d'analyser :
- La dynamique des populations de proies (poissons) et de prédateurs (requins).
- L'impact de la reproduction et de la consommation d'énergie sur la survie des individus.

### Structure du Projet

Le projet est organisé en plusieurs fichiers :

- **Shark.py** : Définition de la classe `Shark`, qui hérite de la classe `Fish` et ajoute des fonctionnalités spécifiques aux requins (manger, gérer l'énergie).
- **Fish.py** : Définition de la classe `Fish`, qui gère les comportements de base des poissons (déplacement, reproduction).
- **environnement.py** : Gère la création et l'affichage de la grille océanique.
- **main.py** : Point d'entrée du programme pour initialiser la grille et lancer la simulation.

### Fonctionnalités des Classes

#### Classe `Fish`

- **Constructeur** : Initialise la position, le compteur de tours pour la reproduction, et le nom de représentation du poisson.
- **Méthodes principales** :
  - `check_and_move()` : Évalue les déplacements possibles autour du poisson et le fait bouger dans une cellule vide.
  - `reproduce()` : Si le poisson atteint un certain nombre de tours, crée un nouveau poisson à une position adjacente.

#### Classe `Shark`

- **Constructeur** : Initialise l'énergie en plus des attributs de la classe `Fish`.
- **Méthodes principales** :
  - `check_and_move()` : Le requin se déplace vers une cellule vide ou mange un poisson pour regagner de l'énergie.
  - `reproduce()` : Reproduit un nouveau requin lorsque le compteur de tours atteint une certaine valeur.
  - `check_energy()` : Vérifie si le requin doit être retiré de la grille en raison d'un manque d'énergie.

### Lancement de la Simulation

Pour lancer la simulation, exécutez le fichier `main.py` qui initialise la grille, place les poissons et les requins, et exécute les itérations de simulation. La grille se met à jour à chaque tour selon les règles définies dans les classes `Fish` et `Shark`.

```bash
python3 main.py
