---
layout: post
title: "2D Game Engine in C++ with Lua Scripting"
date: 2026-02-07 13:53:55 -0500
categories: projects game-dev
image: /assets/posts/2d-game-engine/demo.png
---

This project is a **2D game engine written in C++** with **Lua scripting support**.  
The goal was to design a small but flexible engine that separates core systems from gameplay logic.

**Source code:**  
[github.com/AlexandreAuclair/2D_game_engine_with_c--_and_lua](https://github.com/AlexandreAuclair/2D_game_engine_with_c--_and_lua)

---

## Features
- C++ core engine
- Lua scripting for gameplay logic
- Entity / component-style architecture
- Rendering & update loop separation
- Designed as a learning-focused engine project

---

## Architecture Overview
The engine exposes C++ systems to Lua, allowing game element to be defined without recompiling.

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

Lua scripts control entities placement for levels loading:

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

## What I Learned

- Designing engine architecture in C++
- Binding C++ systems to Lua
- Structuring a medium-size C++ project

---

## Future Improvements

- Scene serialization
- optimizing for allowing more entity without loosing fps
- better tools