---
layout: post
title: "Gun Fight sur NES"
date: 2026-02-13 11:28:55 -0500
categories: projects game-dev
image: assets/posts/GunFight/nes1.PNG
priority: 5
---

Voici un projet que j'ai fait dans mon temps libre où j'ai recréé des classiques du jeu vidéo d'arcade sur la NES en Assembly pour le 6502.
J'ai recréé **Gun Fight**, avec la plus grande précision possible. Ce projet date de 2023.

**Code source:**  
[github.com/AlexandreAuclair/gun-fight-nes](https://github.com/AlexandreAuclair/gun-fight-nes)

---

## Résumé du projet

Après avoir fait **Space Race**, j'ai décidé de refaire un autre jeu d'arcade. Un célèbre jeu de Midway cette fois-ci. Donc la difficulté cette fois venait du fait que le personnage controlé peut tirer 3 balles indépendantes de chacun. Il fallait qu'elles aient leur vélocité et leur position et je voulais pouvoir réutiliser la fonction pour toutes les balles ce qui était compliqué. Il fallait aussi prendre en compte que l'arrière-plan changeait quand le score du joueur 1 ou 2 changeait. Il fallait aussi animer les sprites des joueurs s'ils bougeaient. L'arrière-plan était destructible dans le jeu original donc j'ai dû prendre en compte ça. Le jeu partait une démo si on ne jouait pas qui animais un personnage pour lui faire tirer sur le mur et le faire virer de bord c'est sur ça que j'ai passé la plupart de mon temps.

---

## Technologies utilisées

- **Assembly 6502**
- **Compilateur cc65**
- **fceux pour émuler la console**

---

## Aperçu du projet
![Demo](/assets/posts/GunFight/nes1.PNG)
---
![Demo](/assets/posts/GunFight/nes2.PNG)
---
![Demo](/assets/posts/GunFight/nes3.PNG)
---

## Ce que j’ai appris

Ce projet m’a permis de :
- Apprendre l'Assembly plus profondément
- Comment gérer l'animation de plusieurs sprites
- Gestion de plusieurs objets conceptuels en Assembly

---
