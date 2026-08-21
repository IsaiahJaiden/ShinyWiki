---
title: Claim Commands
description: Full command reference for ShinyVale's claim system.
---

# Claim Commands

Base command: `/claim` (aliases `/territory`). See the [Claims guide](../gameplay/claims.md) for a walkthrough.

| Command | Description |
|---|---|
| `/claim [radius]` | Create a claim around you |
| `/claims` (alias `/territories`) | List/browse claims |
| `/unclaim [claim-name]` (alias `/unterritory`) | Remove a claim |
| `/claim list` | List your claims |
| `/claim see [player]` | Check whose claim you're in |
| `/claim map` | Show a nearby claim map |
| `/claim tp <claim-name>` | Teleport to one of your claims |
| `/claim setspawn` | Set the teleport point for your claim |
| `/claim setname <old> <new>` | Rename a claim |
| `/claim setdesc <claim-name> <description>` | Set a claim description |
| `/claim add [claim-name] <player>` | Trust a player on your claim |
| `/claim remove [claim-name] <player>` | Remove a trusted player |
| `/claim ban [claim-name] <player>` | Ban a player from your claim |
| `/claim unban [claim-name] <player>` | Unban a player |
| `/claim bans [claim-name]` | List banned players |
| `/claim kick [claim-name] <player>` | Remove a player right now |
| `/claim members [claim-name]` | List trusted members |
| `/claim owner [claim-name] <player>` | Transfer claim ownership |
| `/claim settings [claim-name]` | Open the claim settings menu |
| `/claim addchunk <claim-name>` | Add a chunk to a claim |
| `/claim delchunk <claim-name> <chunk>` | Remove a chunk from a claim |
| `/claim merge <claim-1> <claim-2>` | Merge two claims |
| `/claim sell <claim-name> <price>` | List a claim for sale |
| `/claim buy` | Buy a listed claim |
| `/claim cancel <claim-name>` | Cancel a claim sale |
| `/claim main <claim-name>` | Set your main claim |
| `/claim chat <claim-name>` | Open claim-local chat |
| `/claim fly` / `/claim autofly` | Toggle flight inside your claim |

!!! info "Instant trust, no invites"
    `/claim add <player>` adds a trusted member immediately — there's no invitation to accept.
