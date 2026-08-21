---
title: Teleportation & Travel
description: Every way to get around ShinyVale — spawn, random teleport, warps, and player-to-player requests.
---

# Teleportation & Travel

## Quick reference

| Command | What it does |
|---|---|
| `/spawn` | Return to spawn |
| `/rtp` | Teleport to a random location |
| `/warp <name>` | Teleport to a server warp |
| `/pw` | Browse and visit player warps |
| `/tpa <player>` | Request to teleport to a player |
| `/tpaccept` | Accept an incoming teleport request |
| `/tpdeny` | Deny an incoming teleport request |
| `/home` | Open your homes menu — teleport, set, or delete |

## Random teleport

```
/rtp
```

Aliases: `/brtp`, `/randomtp`, `/wild`, `/wildtp`. Drops you somewhere random in the world — the fastest way to find unclaimed land to build on. There's a short cooldown between uses.

!!! tip "The RTP Zone at spawn"
    Standing in the marked RTP Zone near spawn also triggers a random teleport automatically after a short countdown — no command needed, just walk in and wait.

## Server warps

```
/warp <name>
```

ShinyVale's server-wide warps: **spawn, afk, crates, shop, worlds, auction, duels, parkour, leaderboards, rtp, help**.

## Player warps

Want to visit (or create) a player-made destination instead of an official one? See [Player Warps](player-warps.md).

## Homes

```
/home
```

Opens your homes menu — everything about your homes is managed from here, not typed commands. Homes can be set anywhere you like, except spawn and the AFK area.

<div class="sv-grid" markdown>

<div class="sv-card" markdown>
<span class="sv-card-title">:material-bed-empty: Setting a Home</span>
<span class="sv-card-desc">Click an empty grey bed in the menu to set a home at your current location.</span>
</div>

<div class="sv-card" markdown>
<span class="sv-card-title">:material-bed: Teleporting to a Home</span>
<span class="sv-card-desc">Click an existing home's bed to warp there.</span>
</div>

<div class="sv-card" markdown>
<span class="sv-card-title">:material-delete: Deleting a Home</span>
<span class="sv-card-desc">Each home has a dye item sitting just underneath its bed in the menu — <strong>right-click that dye</strong> to delete the home. Left-clicking the bed itself teleports you instead, so make sure you're clicking the dye, not the bed.</span>
</div>

</div>

## Requesting to teleport to another player

```
/tpa <player>
/tpaccept
/tpdeny
```

Sends a request to teleport to someone; they have a couple minutes to accept or deny it before it expires. If you're getting requests you don't want, check [Settings](../commands/general.md) for a way to toggle them off.

## Related pages

- [Claims](claims.md)
- [AFK Area](afk.md)
