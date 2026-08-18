# Backgrounds

A first-person horror game in the collect-and-escape tradition of *Slender*: gather the scattered papers while something hunts you through the map.

This was my first 3D project in Unity, so the scope is deliberately small — the goal was learning the 3D pipeline (terrain, lighting, first-person movement, spatial navigation) rather than shipping a full game.

---

## How it plays

You spawn near the center of the map. On the wall to your left there is a paper — **picking it up starts the game**, and the monster begins hunting you from that moment.

From there it becomes a navigation problem under pressure: find the remaining papers without losing track of where you are, and without cornering yourself in a room with no second exit.

The map is built so that getting lost is a real failure state. There's no minimap and no waypoint — orientation is part of the challenge.

---

## Stack

| | |
|---|---|
| Engine | Unity 6000.0.40f1 |
| Language | C# |
| Rendering | Universal Render Pipeline (URP) |
| Input | Unity Input System |
| Environment | Unity Terrain |

---

## Architecture

```
Assets/Scripts/
├── Monster.cs      # Pursuit behaviour and player tracking
├── Paper.cs        # Pickup interaction and collection state
└── HUDmanager.cs   # HUD and collection counter
```

Scene: `Assets/Scenes/SampleScene.unity`.

---

## Running locally

```bash
git clone https://github.com/EnzoGiacomini/Backgrounds.git
```

Open the folder through **Unity Hub** with editor version `6000.0.40f1`, then load `Assets/Scenes/SampleScene.unity` and press Play.

---

## Credits

The first-person controller comes from the **Unity Starter Assets** package (Unity Asset Store) — it is not my own implementation. Everything under `Assets/Scripts/` is.
