---
layout: post
title: "Sword of Donoma"
date: 2026-02-12 09:53:55 -0500
categories: projects game-dev
image: assets/posts/sword-of-donoma/Capture1.PNG
priority: 5
---

Voici un aperçu de mon projet **Sword of Donoma**, un jeu en développement inspiré des jeux d’action-aventure rétro, avec une forte emphase sur le bas niveau et les contraintes matérielles.

Ce projet met l’accent sur la compréhension approfondie du fonctionnement des systèmes graphiques et des performances en environnement limité.

**Code source :**  
[github.com/AlexandreAuclair/swordOfDonoma](https://github.com/AlexandreAuclair/swordOfDonoma)

---

## Résumé du projet

**Sword of Donoma** est un projet personnel où je développe un jeu en manipulant directement des concepts bas niveau, notamment en environnement de type DOS / 16 bits.

Le projet inclut :
- Un moteur de rendu graphique personnalisé
- La gestion de sprites et de collisions en assembleur
- Une optimisation manuelle des performances
- Une gestion directe de la mémoire et des buffers vidéo

Contrairement à des projets utilisant des moteurs modernes, ici tout est construit “from scratch”, ce qui permet un contrôle total sur le comportement du jeu.

---

## Technologies utilisées

- **C / Assembleur x86 (8088/16 bits)** — logique principale et optimisation bas niveau  
- **DOS / DOSBox-X** — environnement d’exécution  
- **CGA Mode 05h / graphiques bas niveau** — rendu graphique  
- **Outils personnalisés** — conversion d’assets (images, audio)

---

## Aperçu du projet
![Demo](/assets/posts/sword-of-donoma/Capture1.PNG)

![Demo1](/assets/posts/sword-of-donoma/Capture2.PNG)

![Demo2](/assets/posts/sword-of-donoma/Capture3.PNG)

---

## Ce que j’ai appris

Ce projet m’a permis de :

- Comprendre le fonctionnement interne du matériel graphique (framebuffer, palettes, etc.)
- Optimiser du code en assembleur pour des contraintes très strictes
- Implémenter des systèmes fondamentaux de jeu (collision, rendu, input) sans abstraction
- Travailler avec des environnements legacy comme DOS

J’ai également approfondi ma compréhension des compromis entre performance, lisibilité et abstraction, particulièrement en comparaison avec les moteurs modernes.

---