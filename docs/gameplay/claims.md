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
`/claim` `/claims` `/unclaim` `/claim tp <name>` `/claim setname`
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
<span class="sv-card-desc"><code>/claim settings</code> opens a menu of toggles for your claim — PvP, mob spawning, explosions, redstone, fly, item pickup, and more — set separately for members and visitors.</span>
</div>

<div class="sv-card" markdown>
<span class="sv-card-title">:material-map-marker: Set a Home Spot</span>
<span class="sv-card-desc"><code>/claim setspawn</code> sets where <code>/claim tp</code> sends people, and <code>/claim setname</code> gives your claim a proper name instead of a default one.</span>
</div>

</div>

## Expanding and merging

- `/claim addchunk` — add another chunk to an existing claim
- `/claim merge <claim-1> <claim-2>` — combine two of your claims into one

## Selling a claim

Claims can change hands between players:

```
/claim sell <claim-name> <price>
```

List a claim for another player to buy — cancel the listing any time with `/claim cancel <claim-name>`.

## Viewing claims

`/claim map` shows a nearby claim overview, `/claim list` shows all your claims, and `/claim see <player>` checks whose claim you're standing in.

!!! tip "Claims will expire if abandoned"
    If nobody logs into a claim's owner account for an extended period, that claim is automatically freed up — no need to manually clean up an old claim if you're moving on, but don't count on an inactive claim staying reserved forever either.

## Claim rules

Claims exist to protect your stuff — not to be used against other players. Placing a claim purely to block, obstruct, or troll someone else isn't allowed, and staff make the call on what counts as abuse. See the full [Claim Rules](../rules/index.md#claim-rules).

## Full command reference

See [Claim commands](../commands/claims.md) for the complete list.
