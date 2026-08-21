---
title: Claim Commands
description: Full command reference for ShinyVale's claim system.
---

# Claim Commands

Base command: `/claim` (alias `/territory`). See the [Claims guide](../gameplay/claims.md) for a walkthrough of how these fit together.

## Quick reference

| Command | Description |
|---|---|
| `/claim [radius]` | Create a claim around you |
| `/claims` | Browse the claims menu |
| `/unclaim [claim-name]` | Remove a claim |
| `/claim list` | List your claims |
| `/claim see [player]` | Check whose claim you're in |
| `/claim map` · `/claim automap` | Show a nearby claim map |
| `/claim tp <claim-name>` | Teleport to one of your claims |
| `/claim setspawn` | Set the teleport point for your claim |
| `/claim setname <old> <new>` | Rename a claim |
| `/claim setdesc <claim-name> <description>` | Set a claim description |
| `/claim add [claim-name] <player>` | Trust a player |
| `/claim remove [claim-name] <player>` | Remove a trusted player |
| `/claim members [claim-name]` | List trusted members |
| `/claim ban [claim-name] <player>` | Ban a player from your claim |
| `/claim unban [claim-name] <player>` | Unban a player |
| `/claim bans [claim-name]` | List banned players |
| `/claim kick [claim-name] <player>` | Remove a player right now |
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
| `/claim fly` · `/claim autofly` | Toggle flight inside your claim |

---

## Key commands in detail

### `/claim`

**What it does:** Claims the land around you so other players can't build, break, or take things there.

**Usage:** `/claim` or `/claim <radius>`

**Example:** `/claim 3`

**Notes:** Claiming is instant — there's no confirmation prompt — and it's free. Run it with no radius for a default-sized square.

---

### `/claim merge`

**What it does:** Combines two of your claims into a single claim, with one name, one member list, and one settings menu.

**Usage:** `/claim merge <claim-1> <claim-2>`

**Example:** `/claim merge mybase northfield`

**Notes:** Use this whenever you've claimed adjacent plots that are really the same base — managing one claim is far less work than managing three. **Merge before you start changing settings**, especially before disabling teleport access. See the [warning in the Claims guide](../gameplay/claims.md#expanding-and-merging).

---

### `/claim settings`

**What it does:** Opens a menu of toggles controlling what's allowed on your claim — building, interacting, PvP, mob spawning, explosions, flight, teleport visibility, and more.

**Usage:** `/claim settings` or `/claim settings <claim-name>`

**Example:** `/claim settings mybase`

**Notes:** Most settings are configured separately for **Members**, **Visitors**, and **Natural** (environmental) behavior. There's an "apply to all claims" option so you don't have to repeat a setup on every claim. Full list of every toggle: [Claim settings](../gameplay/claims.md#claim-settings).

---

### `/claim add`

**What it does:** Trusts another player on your claim so they can build there.

**Usage:** `/claim add <player>` or `/claim add <claim-name> <player>`

**Example:** `/claim add Steve`

**Notes:** Trust is applied **instantly** — there's no invitation for them to accept. Use `*` in place of a claim name to apply it across all your claims at once. Undo it with `/claim remove`.

---

### `/claim ban` vs `/claim kick`

**What they do:** `ban` blocks a player from entering your claim at all, going forward. `kick` just removes them from the claim right now, without a lasting block.

**Usage:** `/claim ban <player>` · `/claim kick <player>`

**Example:** `/claim ban Griefer123`

**Notes:** Reach for `kick` for a one-off; reach for `ban` when you don't want them coming back. Review who's banned with `/claim bans`.

---

### `/claim tp` and `/claim setspawn`

**What they do:** `setspawn` decides where inside the claim people arrive; `tp` sends you there.

**Usage:** `/claim setspawn` (stand where you want the arrival point) · `/claim tp <claim-name>`

**Example:** `/claim tp mybase`

**Notes:** There's a short delay before the teleport completes.

---

### `/claim sell`

**What it does:** Lists one of your claims for another player to buy, land and all.

**Usage:** `/claim sell <claim-name> <price>`

**Example:** `/claim sell oldbase 50000`

**Notes:** Cancel a listing any time with `/claim cancel <claim-name>`.

!!! info "Instant trust, no invites"
    `/claim add <player>` adds a trusted member immediately — there's no invitation step to accept.
