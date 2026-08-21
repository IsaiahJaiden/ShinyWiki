---
title: Economy & Shop Commands
description: Every money, shop, trading, and auction command on ShinyVale.
---

# Economy & Shop Commands

See the [Economy & Shops](../gameplay/economy.md) and [Auction House](../gameplay/auctions.md) guides for walkthroughs.

## Money

| Command | Aliases | Description |
|---|---|---|
| `/bal` · `/balance` | `/enbal`, `/money` | Check your balance |
| `/baltop` | `/enbaltop` | View the richest players |
| `/pay <player> <amount>` | `/enpay` | Pay another player |
| `/paytoggle` | `/enpaytoggle` | Toggle whether you can receive payments |

## Buying & selling

| Command | Aliases | Description |
|---|---|---|
| `/shop` | — | Open the server shop |
| `/sell` | `/wsell` | Open the sell menu |
| `/worth` | — | Check what an item is worth |
| `/sellhistory` | — | Review what you've sold |
| `/toggleworth` | — | Toggle the worth display |
| `/order` | `/orders`, `/dorder` | Open the bulk sell-order board |
| `/convert` | — | Currency/shard conversion menu |

## Auction house

| Command | Aliases | Description |
|---|---|---|
| `/ah` | `/auction`, `/auctions`, `/ca` | Open the auction house |
| `/ah sell <price>` | — | List the item in your hand |

## Player shops

Your own chest shops are created by **clicking a chest**, not by typing a command — see [Player-owned shops](../gameplay/economy.md#player-owned-shops). Once a shop exists, these commands let you manage it. Stand and look at your shop when running them.

| Command | Description |
|---|---|
| `/qs find <item>` | Find nearby shops selling an item |
| `/qs price <price>` | Change the price of the shop you're looking at |
| `/qs item` | Change what item the shop trades |
| `/qs amount <amount>` | Change how many items per transaction |
| `/qs name <name>` | Give your shop a name |
| `/qs staff add <player>` | Let another player manage your shop |
| `/qs staff del <player>` | Remove a shop staff member |
| `/qs staff list` | List your shop's staff |
| `/qs currency <currency>` | Set which currency the shop uses |
| `/qs about` | QuickShop version info |

The base command `/qs` also answers to `/quickshop`.

!!! info "Making a shop with a command"
    QuickShop also has a `/qs create <price>` command form, but on ShinyVale it currently requires a permission normal players don't have — so **use the chest-click method instead**, which works for everyone. (Staff: this is the `quickshop.create.cmd` node if you ever want to open it up.)

## Trading

| Command | Aliases | Description |
|---|---|---|
| `/trade <player>` | `/axtrade` | Send a direct trade request to another player |

Trades use a confirmation screen on both sides — nothing changes hands until you both confirm. Requests expire after a minute.
