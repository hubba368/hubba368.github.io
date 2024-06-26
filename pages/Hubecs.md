---
layout: default
title: Hub Entity Component System
type: Solo Project
featured: true
tags:
    - OpenGL
    - C++
preface: |
    An in-progress header-only C++ Entity Component System library, originally designed for use with Raylib, but migrated to a more general version for my own use.
images:
    - https://res.cloudinary.com/dwwy1fzms/image/upload/v1719406598/hubecs_k8gs8u.gif
bgImg:
frontImg: https://res.cloudinary.com/dwwy1fzms/image/upload/v1719406598/hubecs_k8gs8u.gif
class: hub
---

{% include pageButton.html buttonName="View On Github (currently private)" url="https://github.com/hubba368/hubECS" %}


After much deliberation, I decided to create my own ECS that I could use for other projects. This project in particular is a Sparse Set implementation, written in C++17.

Not only was this a chance to keep myself learning, but was also a deviation from a lot of my past C++ experience, which was mainly just within Unreal Engine.


### What?

ECS, or _entity-component-system_, is a pattern of code architecture, in the same vein as OOP, where instead of having potentially complex inheritance trees, you have entities (some ID) that have attached components (usually POD) and systems that work with them. 
This project is mainly for my own use, which I made as a learning project for myself, although feel free to use this how you see fit.

This implementation uses a _Sparse Set_ structure, where a _dense_ and _sparse_ set are used for very fast (usually O(1) and O(n) iteration) operations. For this, a sparse set of indexes point to a dense set of Entity IDs and Components.
These sets are stored in Pools which are reserved at compile time, and can be accessed via a _Registry_.
On top of all of this is the _World_, which acts as a single point of entry into the registry, and allows for multiple different ways for iterating on Pools.

Currently, Systems are not handled by the World, but do take a shared_ptr during initialisation so they are able to access entities and components.

#### Basic Example

```cpp
struct Position {
    Vector3 position;
};

class MovementSystem : ISystem {
    
    void OnCreate() override {
        _entities = _world->EntitiesWith<Position>();
    }
    //...
    void Update(float dt) override {

        // use range-for
        for(Entity ent : _entities) {
            auto& pos = _world->GetComponent<Position>(ent);
            // update position
        }

        // use callback
        _world->Each<Position>([&](Entity e, Position& pos) {
            // update position
        });
    }
};


int main() {
    _world = std::make_shared();

    const auto entity = _world->CreateEntity();
    _world->AddComponent<Position>(entity, Position{10f,10f,0f});

    MovementSystem.OnCreate(_world);

    // In some Tick function
    MovementSystem.Update(tick);
}
```
