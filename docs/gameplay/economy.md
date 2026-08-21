---
title: Economy & Shops
description: How money works on ShinyVale — buying, selling, bulk orders, and getting paid.
---

# Economy & Shops

ShinyVale runs on a simple money economy, plus a secondary currency called **shards** used specifically for crate keys.

## The server shop

```
/shop
```

A straightforward buy menu, organized into categories — food, gear, redstone, nether, end items, enchantments, and more. Everything here is bought with money, except the shards category, which sells crate keys and related items for **shards** instead.

## Selling your items

```
/sell
```

Opens a sell menu — drop in what you're carrying and cash it out at the server's set prices.

## Bulk sell orders

```
/order
```

Rather than selling on the spot, `/order` lets you post a standing order for a large quantity of an item at a price you set — other players can then deliver items to fulfill it and get paid directly. You can have up to 26 open orders at once. Good for offloading (or sourcing) large quantities without flooding the instant-sell price.

## Getting paid

<div class="sv-cmd-strip" markdown>
`/pay <player> <amount>` `/baltop` `/paytoggle`
</div>

`/pay` sends money directly to another player. If you don't want to receive payments (or just don't want the spam), turn it off with `/paytoggle`. `/baltop` shows the richest players on the server.

## Player shops

Beyond the server shop, [QuickShop](#player-owned-shops) lets any player set up their own shop by placing a chest — no command needed to create a basic one. See below.

### Player-owned shops

Place a chest, stock it with what you're selling, then:

- **Right-click** the chest holding the item you want to sell, to set it up as a shop selling that item.
- **Left-click** to set it up buying that item from other players instead.

Other players simply click your shop chest to buy or sell. A small tax applies to purchases made at player shops.

## Related pages

- [Auction House](auctions.md) — for one-off listings instead of a standing shop
- [Crates & Keys](../features/crates.md) — what shards are for
- [Economy commands](../commands/economy.md)
