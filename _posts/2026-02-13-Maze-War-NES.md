---
layout: post
title: "Maze War sur NES"
date: 2026-02-13 13:28:55 -0500
categories: projects game-dev
image: assets/posts/MazeWar/nes1.PNG
priority: 5
---

Voici un projet que j'ai fait dans mon temps libre où j'ai recréé des classiques du jeu vidéo sur la NES en Assembly pour le 6502.
J'ai recréé **Maze War**, le premier jeu 3D du mieux que j'ai pu. Ce projet date de 2024.

**Code source:**  
[github.com/AlexandreAuclair/maze-war-nes](https://github.com/AlexandreAuclair/maze-war-nes)

---

## Résumé du projet

Après avoir fait **Space Race**, j'ai décidé de refaire un autre jeu **Maze War**. J'ai commencé en 2023 à regarder comment faire pour créer un environnement 3D. Je suis venu à la conclusion que comme le joueur dans le jeu ne se déplace pas par pixel, mais par case. Il ne voit que des images qui peuvent être dessinées à l'écran. J'avais fait en sorte que la map soit un octet et qu'on puisse bouger dans une case 1x4. C'était rudimentaire, mais ça marchait. En 2024 je suis revenu sur le projet avec pour but de faire la map de **Maze War**. qui dit un labyrinthe dit aussi plusieurs entrés donc j'ai recommencé l'afficheur du début en gardant le même principe. J'ai aussi pris un bitmap pour représenter la carte de **Maze War**. Ce projet était vraiment plus sur comment on organise les données pour données l'impression que le joueur est dans un labyrinthe 3D à place d'un bitmap.

---

## Technologies utilisées

- **Assembly 6502**
- **Compilateur cc65**
- **fceux pour émuler la console**

---

## Aperçu du projet
![Demo](/assets/posts/MazeWar/nes1.PNG)
---
![Demo](/assets/posts/MazeWar/nes2.PNG)
---
![Demo](/assets/posts/MazeWar/map.PNG)
---

## Ce que j’ai appris

Ce projet m’a permis de :
- Apprendre l'Assembly plus profondément
- comment gérer des données en quantité innombrable

---
