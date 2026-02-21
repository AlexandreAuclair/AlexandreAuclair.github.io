---
layout: post
title: "Blockade sur NES"
date: 2026-02-13 14:28:55 -0500
categories: projects game-dev
image: assets/posts/Blockade/nes1.PNG
priority: 5
---

Voici un projet que j'ai fait dans mon temps libre où j'ai recréé des classiques du jeu vidéo sur la NES en Assembly pour le 6502.
J'ai recréé **Blockade**, un jeu type puzzle joueur contre joueur. Ce projet date de 2024.

**Code source:**  
[github.com/AlexandreAuclair/blockade](https://github.com/AlexandreAuclair/blockade)

---

## Résumé du projet

Après avoir fait **Gun Fight**, j'ai décidé de refaire un autre jeu **Blockade**. C'est le jeu qui a inspiré les batailles de moto du film Tron. Le but de ce projet était de faire un autre jeu sur la NES pour voir comment faire bouger l'arrière-plan, jusqu'à maintenant j'utilisais le système des sprites, mais comme tu ne peux avoir que 64 sprites sur l'écran et que 8 sur une même ligne, je me devais d'utiliser les sprites sur l'arrière-plan. Ce qui est difficile est que tu dois écrire les changements pendant un moment précis et donc je devais calculer le temps que prenaient les opérandes à exécuter sur le CPU.

---

## Technologies utilisées

- **Assembly 6502**
- **Compilateur cc65**
- **fceux pour émuler la console**

---

## Aperçu du projet
![Demo](/assets/posts/Blockade/nes1.PNG)
---
![Demo](/assets/posts/Blockade/nes2.PNG)

---

## Ce que j’ai appris

Ce projet m’a permis de :
- Apprendre l'Assembly plus profondément
- Contrôle du code pour gérer une boucle main et les intérruptions machine
- Gestion des cycles des opérandes dans le code

---
