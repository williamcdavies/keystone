---
tags:
  - CS381
---
Entity component system is a software architectural pattern used in video game development for the representation of game world objects.

## Characteristics

### Entity 
An entity represents a general-purpose object. In a game engine context, for example, every coarse game object is represented as an entity. Usually, it only consists of a unique ID. Implementations typically use a plain integer for this.

### Component
A component characterises an entity as possessing a particular aspect, and holds the data needed to model that aspect. For example, every game object that can take damage might have a Health component associated with its entity. Implementations typically use [[Structures]], [[Classes]], or associative arrays.

### System
A system is a process that acts on all entities with the desired components. For example, a physics system may query for entities having mass, velocity and position components, iterate over the results, and do physics calculations for each entity using the set of components.