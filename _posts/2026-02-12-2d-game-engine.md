---
layout: post
title: "2D-game-engine"
date: 2026-02-12 09:53:55 -0500
categories: projects game-dev
image: assets/posts/2d-game-engine/Capture1.PNG
priority: 4
---

Voici un aperçu de mon projet **GauntletClone**, développé à l’Université de Sherbrooke durant l’automne 2023.  
Ce projet est conçu comme un jeu vidéo prototype pour le cours IFT215 où j'ai utilisé le temps donné pour faire une application avec interface utilisateur pour faire ce jeu.

**Code source:**  
[github.com/AlexandreAuclair/2D-game-engine](https://github.com/AlexandreAuclair/2D-game-engine)

---

## Résumé du projet

Pour mon cours IFT215 de l'université de Sherbrooke, j'ai fait ce jeu qui est un moteur de jeu qui utilise les cartes créées sur Tilemap et qui utilisent un analyseur de fichier XML pour lire les cartes.
J'ai aussi fait mon propre moteur de jeu pour commencer le jeu et donc j'ai implémenté toutes les mathématiques de formes vectorielles moi-même.
J'avais aussi implémenté tous les appels de SDL2 par moi-même pour les graphiques 2D et autres textures. Mon plus gros problème était que j'avais utilisé le système de class orienté objet de C++ qui n'était pas idéal.
---

## Technologies utilisées

- **C++** — code source  
- **SDL2** — lien avec la bibliothèque win32 pour Windows
- **SDL2_images** — gérer les textures
- **Tilemap** — gestion de carte pour développement game dev

---

## Aperçu du projet
![Demo](/assets/posts/2d-game-engine/Capture1.PNG)

---

## Ce que j’ai appris

Ce projet m’a permis de :
- Comprendre comment faire un jeu avec C++ sur Windows
- Structurer un projet C++
- Travailler avec SDL2 et C++
- Mettre en place une architecture modulaire et réutilisable


J’ai également compris comment le modèle orienté objet est fragile. Par conséquent, dans un projet subséquent de nature similaire,
j’ai adopté une approche méthodologique différente.

---
