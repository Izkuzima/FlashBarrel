# FlashBarrel

Adds **yaw, pitch, and roll** recording/playback support to [Flashback](https://modrinth.com/mod/flashback) replays, in sync with the [Do a Barrel Roll](https://modrinth.com/mod/do-a-barrel-roll) mod (DABR).

When you record a Flashback replay, the vanilla player's camera converges with DABR's roll rather than fighting it — the recorded roll is stored and replayed so your rolls play back exactly as they happened, with no jitter and no snapping.

---

## Features

- **Full orientation recording** — yaw and pitch plus DABR roll are captured together as quaternions, so playback stays fluent even through vertical flight, loops, and barrel rolls.
- **Roll in the replay GUI** — the recorded roll is surfaced as Flashback's camera roll override, so you can see your true roll while scrubbing/playing back.
- **Configurable sample rate** — 20 / 60 / 120 / 240 / 360 samples per tick (Mod Menu → FlashBarrel). 20 is the default; **60 is recommended** for fast turns.

![badge-client](https://img.shields.io/badge/-client--side-1976d2)
![badge-fabric](https://img.shields.io/badge/-Fabric-dbd0b4)

---


## Requirements

- **Client-only** — works in singleplayer and multiplayer (including vanilla servers, no server mod required)
- Minecraft **1.21 – 26.x** (Fabric), see supported versions below
- Fabric API
- [Flashback](https://modrinth.com/mod/flashback) (same MC version)
- [Do a Barrel Roll](https://modrinth.com/mod/do-a-barrel-roll)
- Optional: Mod Menu + Cloth Config (`config/flashbarrel.json` can be edited manually)

> The mod is client-side (`environment: "client"`). Install it only in the client/modpack folder.

---

## Download

Get the latest jar from [Modrinth](https://modrinth.com/mod/flashbarrel). Releases are not distributed anywhere else.

---

## Configuration

Stored at `config/flashbarrel.json` in your game directory (created on first launch):

```json
{
  "rollUpdatesPerSecond": 380
}
```

| Samples per tick | `rollUpdatesPerSecond` |
|------------------|------------------------|
| 20 (default)     | 380                    |
| **60 (recommended)** | **1180**           |
| 120              | 2380                   |
| 240              | 4780                   |
| 360              | 7180                   |

Higher rates reduce interpolation error during fast simultaneous yaw+roll (measurable to <0.3° at 360 samples/tick); 60 is a good balance of accuracy and file size.

---

## Modpacks

You are welcome to include FlashBarrel in any modpack, including offline packs that bundle the jar directly. No permission needed.

---