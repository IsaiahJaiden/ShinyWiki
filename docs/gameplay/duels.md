---
title: Duels & PvP
description: Challenge another player to a 1v1, queue for a match, and build your own kits.
---

# Duels & PvP

Want a fair fight? ShinyVale's duel system lets you challenge another player directly or queue up for a match, completely separate from open-world PvP.

## Challenging a player

```
/duel <player>
```

Alias: `/1v1`. Sends a direct challenge — if they accept, you're both teleported into an arena for a 1v1.

## Queueing for a match

```
/queue
```

Alias: `/q`. Joins the matchmaking queue instead of challenging someone specific — you'll be paired with the next available opponent.

## Kits

```
/kit
```

Alias: `/dkit`. Duels are fought with kits — pre-set loadouts you (or the server) define. Use `/kit edit <kitname>` to customize your own, and `/kit reset <kitname>` to reset one back to default.

## Parties & spectating

<div class="sv-cmd-strip" markdown>
`/party` `/spectate`
</div>

Team up with friends before queueing using `/party` (alias `/p`, `/duelparty`, `/dp`), or watch an ongoing match with `/spectate` (alias `/spec`).

## Checking your stats

```
/duel stats
```

Shows your rating per kit, plus your recent match history.

!!! warning "A few things change mid-duel"
    Some commands (like `/heal`, `/kit`, and enderchest access) are blocked while you're actively in a match, and ender pearls stop working in the closing phase of a match. This keeps duels fair — it's not a bug if a command suddenly doesn't work mid-fight.

## Related pages

- [Bounties](bounties.md)
- [Duel commands](../commands/duels-bounties.md)
