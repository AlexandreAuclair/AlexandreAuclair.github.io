---
layout: post
title: "Space Race on NES"
date: 2026-02-13 09:53:55 -0500
categories: projects game-dev
image: assets/posts/SpaceRace/nes1.PNG
---

voici un projet que j'ai fait dans mon temps libre où j'ai recréer des classiques d'Atari sur la NES en assembly pour le 6502.
J'ai recréer **Space Race** du mieux que j'ai pus. Ce projet date de 2023.

**Code source:**  
[github.com/AlexandreAuclair/2D-game-engine](https://github.com/AlexandreAuclair/space-race-nes)

---

## Résumé du projet

Après avoir fait **Pong** j'ai décidé de refaire un autre jeu d'Atari. C'est pour finalement prendre ce que j'ai fait dans le jeu **Pong** et l'augmenter à un autre jeu. Le but c'est si je complique le jeu c'est plus compliquer à coder, donc j'apprends encore plus de cette manière. Donc faire pour faire **Space Race** la différence c'est qu'il faut calculer un temps de jeu parce que le jeu à un timer. Le jeu à aussi plus de collision qui sont supposé être des astéroïdes. Elles sont réprésenté par 2 pixels collé ensemble 
et qui vont dans des directions différentes et à des vitesse différente.

---

## Technologies utilisées

- **Assembly 6502**
- **Compilateur cc65**
- **fceux pour emuler la console**

---

## Aperçu du projet
![Demo](/assets/posts/SpaceRace/nes1.PNG)
---
![Demo](/assets/posts/SpaceRace/nes2.PNG)

---

## Ce que j’ai appris

Ce projet m’a permis de :
- Apprendre l'assembly plus profondement
- comment gérer plus de collision
- gestion d'un timer en assembly

---
