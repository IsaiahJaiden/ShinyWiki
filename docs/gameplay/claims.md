---
title: Claims
description: Protect your base with ShinyVale's claim system — creating, managing, and trusting players on your land.
---

# Claims

Claiming protects your builds from other players — no build/break, no item pickup, no PvP (unless you allow it) inside your claimed land, until you say otherwise.

!!! info "Protection everywhere, claims where it matters"
    ShinyVale's worlds run in normal survival mode — you can build anywhere, claimed or not. Claiming is what adds protection on top, not a requirement to build at all.

## Creating a claim

```
/claim
```

Run it with no arguments to claim a default square area around you, or give it a radius:

```
/claim <radius>
```

Claiming is instant — no confirmation screen, and by default it's completely free.

<div class="sv-cmd-strip" markdown>
`/claim` `/claims` `/unclaim` `/claim tp <name>` `/claim setname` `/claim merge` `/claim settings`
</div>

## Managing your claim

<div class="sv-grid" markdown>

<div class="sv-card" markdown>
<span class="sv-card-title">:material-account-multiple-plus: Trusting Players</span>
<span class="sv-card-desc"><code>/claim add &lt;player&gt;</code> adds someone as a trusted member instantly — no invite step to accept. <code>/claim remove &lt;player&gt;</code> takes it back.</span>
</div>

<div class="sv-card" markdown>
<span class="sv-card-title">:material-account-cancel: Banning/Kicking</span>
<span class="sv-card-desc"><code>/claim ban &lt;player&gt;</code> blocks someone from entering entirely. <code>/claim kick &lt;player&gt;</code> just removes them right now without a lasting ban.</span>
</div>

<div class="sv-card" markdown>
<span class="sv-card-title">:material-cog: Claim Settings</span>
<span class="sv-card-desc"><code>/claim settings</code> opens a full menu of toggles for your claim — see <a href="#claim-settings">Claim settings</a> below for the complete list.</span>
</div>

<div class="sv-card" markdown>
<span class="sv-card-title">:material-map-marker: Set a Home Spot</span>
<span class="sv-card-desc"><code>/claim setspawn</code> sets where <code>/claim tp</code> sends people, and <code>/claim setname</code> gives your claim a proper name instead of a default one.</span>
</div>

</div>

## Expanding and merging

If your base grows past your original claim, you don't have to live with two separate, disconnected claims forever.

- `/claim addchunk <claim-name>` — add another chunk onto an existing claim
- `/claim merge <claim-1> <claim-2>` — combine two of your claims into a single claim

Merging is the better option any time you've claimed adjacent plots that really belong to the same base. Once merged, the whole area behaves as **one claim** — one name, one set of members, one settings menu — instead of you having to manage two (or more) claims separately every time you want to change something.

!!! warning "Merge first, then lock down settings"
    If you're planning to merge claims, do the merge **before** you configure settings like disabling teleportation. Changing settings — especially turning off teleport access — on a claim before it's been merged can cause problems once the claims are combined. Get the merge done first, confirm everything looks right, and only then start adjusting toggles like GuiTeleport.

## Claim settings

```
/claim settings
```

Opens a menu of toggles that control exactly what is and isn't allowed on your claim. Most settings are configured **separately for three groups**, so you can be more permissive with people you trust than with strangers:

- **Members** — players you've added with `/claim add`
- **Visitors** — anyone else who walks onto your claim
- **Natural** — environmental behavior that isn't tied to a specific player at all (explosions, fire, mob spawning, and so on)

There's also an "apply to all claims" option in the menu, so you don't have to repeat the same setup on every claim you own one at a time.

### Building & breaking

| Setting | Controls |
|---|---|
| Build | Placing blocks |
| Destroy | Breaking blocks |
| Special Blocks | Breaking sensitive blocks like spawners |

### Interacting

| Setting | Controls |
|---|---|
| Buttons | Using buttons |
| Levers | Using levers |
| Plates | Stepping on pressure plates |
| Doors | Opening doors |
| Trapdoors | Opening trapdoors |
| Fence Gates | Opening fence gates |
| Tripwires | Triggering tripwires |
| Repeaters/Comparators | Adjusting redstone repeaters and comparators |
| Bells | Ringing bells |
| Interact Blocks | Using containers and other interactive blocks (furnaces, chests, and similar) |
| Entities | Interacting with entities (leashing, feeding, etc.) |

### Items

| Setting | Controls |
|---|---|
| Items Pickup | Picking up dropped items |
| Items Drop | Dropping items |

### Movement & access

| Setting | Controls |
|---|---|
| Enter | Whether the group can enter the claim at all |
| Teleportations | Teleporting directly into the claim |
| GuiTeleport | Whether the claim shows up as a teleport option in the `/claims` menu — see the merge warning above before touching this one |
| Fly | Flying while inside the claim |
| Elytra | Elytra gliding inside the claim |
| Portals | Using nether/end portals inside the claim |
| Windcharges | Using wind charges inside the claim |

### Combat & mobs

| Setting | Controls |
|---|---|
| Pvp | Player vs. player combat |
| Monsters | Hostile mob spawning |
| Damages | Taking damage in general |

### Environment (Natural)

| Setting | Controls |
|---|---|
| Explosions | Explosion damage/block breakage |
| Liquids | Water and lava flow |
| Redstone | Redstone circuits running |
| Frostwalker | Frost Walker boot effect |
| Firespread | Fire spreading |
| Weather | Weather effects inside the claim |

## Selling a claim

Claims can change hands between players:

```
/claim sell <claim-name> <price>
```

List a claim for another player to buy — cancel the listing any time with `/claim cancel <claim-name>`.

## Viewing claims

`/claim map` shows a nearby claim overview, `/claim list` shows all your claims, and `/claim see <player>` checks whose claim you're standing in.

!!! tip "Claims will expire if abandoned"
    If a claim's owner doesn't log in for **2 weeks**, that claim is automatically freed up — no need to manually clean up an old claim if you're moving on, but don't count on an inactive claim staying reserved past that point either.

## Claim rules

Claims exist to protect your stuff — not to be used against other players. Placing a claim purely to block, obstruct, or troll someone else isn't allowed, and staff make the call on what counts as abuse. See the full [Claim Rules](../rules/index.md#claim-rules).

## Full command reference

See [Claim commands](../commands/claims.md) for the complete list.
