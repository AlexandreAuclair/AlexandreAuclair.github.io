---
layout: post
title: "Space Race on NES"
date: 2026-02-13 09:53:55 -0500
categories: projects game-dev
image: assets/posts/SpaceRace/nes1.PNG
priority: 5
---

Voici un projet que j'ai fait dans mon temps libre où j'ai recréé des classiques d'Atari sur la NES en Assembly pour le 6502.
J'ai recréé **Space Race** du mieux que j'ai pu. Ce projet date de 2023.

**Code source:**  
[github.com/AlexandreAuclair/space-race-nes](https://github.com/AlexandreAuclair/space-race-nes)

---

## Résumé du projet

Après avoir fait **Pong**, j'ai décidé de refaire un autre jeu d'Atari. C'est pour finalement prendre ce que j'ai fait dans le jeu **Pong** et l'optimiser dans un autre jeu. Le but c'est si je complique le jeu c'est plus compliqué à coder, donc j'apprends encore plus de cette manière. Donc, pour faire **Space Race** la différence c'est qu'il faut calculer un temps de jeu parce que le jeu à une minuterie. Le jeu a aussi plus de collision avec ce qui est censée être des astéroïdes. Elles sont réprésentées par 2 pixels collés ensemble et qui vont dans des directions différentes et à des vitesses différentes.

---

## Technologies utilisées

- **Assembly 6502**
- **Compilateur cc65**
- **fceux pour émuler la console**

---

## Aperçu du projet
![Demo](/assets/posts/SpaceRace/nes1.PNG)
---
![Demo](/assets/posts/SpaceRace/nes2.PNG)

---

## Ce que j’ai appris

Ce projet m’a permis de :
- Apprendre l'Assembly plus profondément
- Comment gérer plus de collisions
- Gestion d'un chronomètre en Assembly

---
