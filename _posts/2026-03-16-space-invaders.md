---
layout: post
title: "Space Invader on CGA"
date: 2026-03-15 09:53:55 -0500
categories: projects game-dev
image: assets/posts/space-Invader/cga1.PNG
priority: 5
---

Voici un projet que j'ai fait dans mon temps libre où j'ai recréé le jeu Space Invader pour la CGA qui est un ancienne carte graphique du IBM PC 5150.

**Code source:**  
[github.com/AlexandreAuclair/spaceInvader](https://github.com/AlexandreAuclair/spaceInvader)

---

## Résumé du projet

C'est dernier temps j'ai travailler sur de l'ancien DOS, j'ai décidé de refaire un autre jeu d'arcade. Donc j'ai commencé à coder en C Space Invader pour la carte graphique CGA du IBM PC 5150. Je me suis servi du compilateur BorlandC++ 3.1 pour compiler mon code C pour l'ancienne machine. Comme il n'y a pas beaucoup de tutoriel pour faire des graphique sur la carte CGA. J'ai du faire mes propres recherches avec des livres des années '80. J'ai aussi du changé le isr du keyboard, car il n'accepte qu'une touche à la fois ce qui est dérangeant quand tu ne veux pas une liste de clé touché, mais juste laquel est préssé en ce moment.

---

## Technologies utilisées

- **language C**
- **Compilateur BorlandC 3.1**
- **dosbox-x pour émuler l'ordinateur**

---

## Aperçu du projet
![Demo](/assets/posts/space-Invader/cga1.PNG)

---

## Ce que j’ai appris

Ce projet m’a permis de :
- d'approfondir mes connaissance en C.
- de savoir comment représenter des sprites sur la CGA.
- d'abstraire mon code pour pouvoir rappeler plusieurs partie différentes.

---
