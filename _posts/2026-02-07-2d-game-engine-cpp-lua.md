---
layout: post
title: "2D Game Engine in C++ with Lua Scripting"
date: 2026-02-07 13:53:55 -0500
categories: projects game-dev
image: assets/posts/2d-game-engine/demo.PNG
priority: 2
---

Ce projet est un **moteur de jeu 2D écrit en C++** avec **prise en charge du langage de script Lua**.

L'objectif était de concevoir un moteur léger, mais flexible, séparant les systèmes principaux de la logique de jeu.

**Code source:**  
[github.com/AlexandreAuclair/2D_game_engine_with_c--_and_lua](https://github.com/AlexandreAuclair/2D_game_engine_with_c--_and_lua)

---

## Fonctionnalités
- Moteur C++ principal
- Scripting Lua pour les elements de level
- Architecture de type entité/composant
- Séparation des boucles de rendu et de mise à jour
- Conçu comme un projet de moteur axé sur l'apprentissage

---

## Aperçu de l'architecture

Le moteur expose les systèmes C++ à Lua, permettant ainsi de définir des éléments de jeu sans recompilation.

```cpp
void Game::Update() {
    // Frame cap
    int timeToWait = MILLISECS_PER_FRAME - (SDL_GetTicks() - millisecsPreviousFrame);
    if (timeToWait > 0 && timeToWait <= MILLISECS_PER_FRAME) {
        SDL_Delay(timeToWait);
    }

    double deltaTime = (SDL_GetTicks() - millisecsPreviousFrame) / 1000.0;
    millisecsPreviousFrame = SDL_GetTicks();

    // Reset event handlers for the current frame
    eventBus->Reset();

    // Perform the subscription of the events for all systems
    //registry->GetSystem<MovementSystem>().SubscribeToEvents(eventBus);
    registry->GetSystem<GodMovementSystem>().SubscribeToEvents(eventBus);
    //....
    
    // Apply pending entity add/remove
    registry->Update();

    profiler.Begin("GodMovementSystem");
    registry->GetSystem<GodMovementSystem>().Update(eventBus, registry, camera);
    profiler.End("GodMovementSystem");

    //...

    GameManager::checkForWinCondition();
}
```

Des scripts Lua contrôlent le placement des entités pour le chargement des niveaux:

```lua
Level = {
    ----------------------------------------------------
    -- Table to define the list of assets
    ----------------------------------------------------
    assets = {
        [0] =
        --...
        { type = "texture", id = "bullet-texture",              file = "./assets/images/bulletImpact.png" },
        { type = "texture", id = "flamme-texture",              file = "./assets/images/flammeTrhowerFX.png" },
        { type = "texture", id = "marine-texture",              file = "./assets/images/soldat-spritesheetv1.png", multipleColor = true },
        { type = "texture", id = "flammer-texture",             file = "./assets/images/burner-spritesheet.png", multipleColor = true },
        { type = "texture", id = "worker-texture",              file = "./assets/images/worker-spritesheet.png", multipleColor = true },
        { type = "texture", id = "home-texture",                file = "./assets/images/Home-Spritesheet.png", multipleColor = true },
        { type = "texture", id = "farm-texture",                file = "./assets/images/Farm-Spritesheet.png", multipleColor = true },
        { type = "texture", id = "barrack-texture",             file = "./assets/images/Barrack-Spritesheet.png", multipleColor = true },
        { type = "texture", id = "crystal-texture",             file = "./assets/images/crystal.png" },
        { type = "texture", id = "crystal2-texture",             file = "./assets/images/crystal3.png" },
        { type = "font"   , id = "pico8-font-5",                file = "./assets/fonts/pico8.ttf", font_size = 5 },
        { type = "font"   , id = "pico8-font-10",               file = "./assets/fonts/pico8.ttf", font_size = 10 }
    },
}
```
---

## Screenshots

![Demo](/assets/posts/2d-game-engine/demo.PNG)

---

## Ce que j'ai appris
- Conception de l'architecture du moteur en C++
- Liaison de systèmes C++ avec Lua
- Structuration d'un projet C++ de taille moyenne

---

## Améliorations futures
- Sérialisation des scènes
- Optimisation pour permettre un plus grand nombre d'entités sans perte de FPS
- Meilleurs outils pour le projet