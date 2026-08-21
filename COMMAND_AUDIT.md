# ShinyVale Command Audit

**Audit date:** 2026-08-21 · Companion to [PLUGIN_AUDIT.md](PLUGIN_AUDIT.md)

Evidence keys: `PY` = plugin's own `plugin.yml`/`paper-plugin.yml` · `CFG` = active plugin config · `LP` = LuckPerms `default` group · `LOG` = startup log · `ESS` = Essentials `config.yml` `player-commands:` whitelist

---

## Published player commands

| Command | Aliases | Plugin | Ver | Access | Evidence |
|---|---|---|---|---|---|
| `/claim [radius]` + subcommands | `/territory` (CFG) | SimpleClaimSystem | 1.12.3.3 | PUBLIC | PY `scs.command.claim` default true; LP grants `scs.command.claim.*` |
| `/claims` | `/territories` (CFG) | SimpleClaimSystem | 1.12.3.3 | PUBLIC | PY default true |
| `/unclaim [name]` | `/unterritory` (CFG) | SimpleClaimSystem | 1.12.3.3 | PUBLIC | PY default true |
| `/rtp` | `/brtp` `/randomtp` `/wild` `/wildtp` `/betterrtp` | BetterRTP | 3.6.13 | PUBLIC | PY aliases list; `betterrtp.use` default true |
| `/warp <name>` | none¹ | DonutWarp | 3.0 | PUBLIC | PY, no permission node |
| `/spawn` | — | EssentialsXSpawn | 2.22.0 | PUBLIC | LP `essentials.spawn`; ESS |
| `/home`, `/homes` | — | DonutHomes | 3.0 | PUBLIC | PY; LP `home.use`, `homes.default` |
| `/sethome` | — | DonutHomes | 3.0 | PUBLIC | PY, no permission node |
| `/delhome`, `/renamehome` | — | EssentialsX | 2.22.0 | PUBLIC | ESS whitelist |
| `/tpa` `/tpahere` `/tpaccept` `/tpacancel` `/tpauto` `/tptoggle` | — | DonutTP | 3.0 | PUBLIC | PY, no permission nodes; LP also grants Essentials equivalents |
| `/tpdeny` | `/tpno` `/etpno` `/etpdeny` | EssentialsX | 2.22.0 | PUBLIC | PY aliases; ESS whitelist |
| `/back` | `/return` | EssentialsX | 2.22.0 | PUBLIC | ESS whitelist (`back`, `back.ondeath`) |
| `/pw` | `/playerwarp(s)` `/pwarp(s)` `/axpw` `/axplayerwarps` | AxPlayerWarps | 1.12.0 | PUBLIC | CFG alias list; LP `axplayerwarps.{use,create,help,warps.20}` |
| `/shop` | — | DonutShop | 3.0 | PUBLIC | PY, no permission node |
| `/sell` | `/wsell` | DonutWorth | 1.5.2 | PUBLIC | PY (`wsell` primary, `sell` alias) |
| `/worth` | — | DonutWorth | 1.5.2 | PUBLIC | PY; also ESS whitelist |
| `/sellhistory`, `/toggleworth` | — | DonutWorth | 1.5.2 | PUBLIC | PY, no permission node |
| `/order` | `/orders` `/dorder` | DonutOrder | 1.12.1 | PUBLIC | PY; LP `order.default` |
| `/pay` | `/enpay` | EnhancedPay | 2.3 | PUBLIC | PY; LP `epay.use` |
| `/bal`, `/balance` | `/enbal` `/money` | EnhancedPay | 2.3 | PUBLIC | PY |
| `/baltop` | `/enbaltop` | EnhancedPay | 2.3 | PUBLIC | PY |
| `/paytoggle` | `/enpaytoggle` | EnhancedPay | 2.3 | PUBLIC | PY |
| `/ah` | `/auction(s)` `/ca` `/crazyauction(s)` | CrazyAuctions | 1.7.0 | PUBLIC | PY aliases; LP `crazyauctions.access/view/sell` |
| `/ah sell <price>` | — | CrazyAuctions | 1.7.0 | PUBLIC | CFG in-GUI hint text |
| `/duel <player>` | `/1v1` | Duels | 7.6 | PUBLIC | `commands.yml`; `duels.duel` default true |
| `/queue` | `/q` | Duels | 7.6 | PUBLIC | `commands.yml`; LP `duels.*` |
| `/kit` | `/dkit` | Duels | 7.6 | PUBLIC | `commands.yml` |
| `/party` | `/p` `/duelparty` `/dp` | Duels | 7.6 | PUBLIC | `commands.yml` |
| `/spectate` | `/spec` | Duels | 7.6 | PUBLIC | `commands.yml` |
| `/duels` | `/ds` | Duels | 7.6 | PUBLIC | `commands.yml` |
| `/bounty <player> [amt]` | none¹ | DonutBounty | 3.0 | PUBLIC | PY, no permission node |
| `/bountytoggle` | — | DonutBounty | 3.0 | PUBLIC | PY |
| `/vote` | none² | VotingPlugin | 6.19 | PUBLIC | PY; LOG "Giving VotingPlugin.Player permission by default" |
| `/votetotal` `/votenext` `/votelast` `/votetop` `/votebest` `/votestreak` `/votetoday` `/votehelp` | `/vtotal` `/vnext` `/vlast` `/vtop` `/vbest` `/vstreak` `/vtoday` `/vhelp` | VotingPlugin | 6.19 | PUBLIC | PY |
| `/msg` | `/w` `/tell` `/pm` | EssentialsX | 2.22.0 | PUBLIC | LP `essentials.msg`; ESS |
| `/r` | `/reply` | EssentialsX | 2.22.0 | PUBLIC | LP `essentials.reply`; ESS |
| `/mail`, `/me`, `/nick`, `/ignore`, `/helpop` | — | EssentialsX | 2.22.0 | PUBLIC | ESS whitelist |
| `/afk` | `/eafk` `/away` | EssentialsX | 2.22.0 | PUBLIC | PY aliases; LP `essentials.afk` |
| `/list`, `/seen`, `/realname`, `/near`, `/getpos`, `/depth`, `/compass`, `/time`, `/itemdb`, `/suicide`, `/motd` | various | EssentialsX | 2.22.0 | PUBLIC | ESS whitelist |
| `/seed` | — | Worlds | 3.10.5 | PUBLIC | LP grants **both** `minecraft.command.seed` and `worlds.command.seed` |
| `/sit` `/lay` `/layback` `/bellyflop` `/spin` `/crawl` | `/gsit` `/glay` etc. | GSit | 3.1.0 | PUBLIC | PY aliases; LP `gsit.*` |
| `/teams` | `/team` | DonutTeams | 3.1.4 | PUBLIC | PY, no permission node |
| `/teamtoggle` | — | DonutTeams | 3.1.4 | PUBLIC | PY |
| `/settings` | — | DonutSettings | 3.1.2 | PUBLIC | PY, no permission node |
| `/ping` | — | DonutPing | 2.1.1 | PUBLIC | PY, no permission node |
| `/stats` | — | EnhancedStats | 1.0 | PUBLIC | PY, no permission node |
| `/nightvision` | `/nv` | DonutNightvision | 2.0 | PUBLIC | PY, no permission node |
| `/phantom` | — | DonutPhantoms | 2.0 | PUBLIC | PY, no permission node |
| `/togglespawnmessages` | — | MooshySpawn | 1.0.0 | PUBLIC | PY, no permission node |
| `/fastercrystals <on\|off\|toggle>` | — | FasterCrystals | 2.1.0 | PUBLIC | PY usage string; LP `fastercrystals.toggle` |
| `/tab scoreboard` | — | TAB | 5.4.0 | CONDITIONAL | PY `tab.scoreboard.toggle` default op, **but LP grants it** |
| `/leaderboard` | none³ | LeaderboardMaker | 3.1 | PUBLIC | PY; LP `leaderboardmaker.use` |
| `/skin` | — | SkinsRestorer | 15.12.5 | PUBLIC | LP `skinsrestorer.command.*` (commands registered dynamically) |
| `/ss prices` | `/smartspawner` `/spawner` | SmartSpawner | 1.5.3 | PUBLIC | PY `smartspawner.prices` default true |
| `/enchanter` | `/ce` `/crazyenchantments` | CrazyEnchantments | 2.7.2 | PUBLIC | PY aliases; LP `crazyenchantments.gui` |
| `/tinkerer` | `/tinker` | CrazyEnchantments | 2.7.2 | PUBLIC | PY; LP `.tinker` |
| `/gkit` | `/gkitz` `/gkits` | CrazyEnchantments | 2.7.2 | PUBLIC | PY (**`gkit` is primary**, not `gkits`) |
| `/calendar` | `/axcalendar` `/adventcalendar` `/axadventcalendar` | AxCalendar | 2.6.0 | PUBLIC | CFG `command-aliases` |
| `/guide`, `/media`, `/convert`, `/billford`, `/commoncratefordonutsmp` | — | DeluxeMenus | 1.14.1-DEV | PUBLIC | Menu files with `register_command: true` |
| `/discord` | `/discordsrv` | DiscordSRV | 1.30.4 | PUBLIC | PY |

¹ Declared under the invalid key `alias:` (singular) instead of `aliases:` — almost certainly never registers. Base command unaffected.
² `/v` is **not** declared anywhere. Previously published in error; removed.
³ `/leaderboards` is **not** declared. Previously published in error; removed. (The names `baltop`, `topshards`, etc. are internal menu aliases inside `/leaderboard`, not Bukkit commands.)

---

## Deliberately NOT published

| Command(s) | Reason |
|---|---|
| `/envoys` `/envoy` `/crazyenvoys` | **Plugin fails to enable at runtime** (LOG). Was published in error — now removed. |
| `/fly` | LP **explicitly denies** `essentials.fly` and `flyformvps` (`value: false`). Only `/claim fly` (in-claim) is real. |
| `/shopkeeper(s)` | Plugin never loads (not Folia-marked). |
| `/headdb` `/hdb` | Plugin never loads (not Folia-marked). |
| `/ah bid` | LP denies `crazyauctions.bid`; also `Bidding: false` in CFG. Doubly off. |
| `/findplayer` | Technically open (no permission node) but reveals another player's location — moderation-shaped. Flagged for owner decision. |
| `/itemedit` `/itemstorage` `/serveritem` | No permission nodes declared at all, but NBT/lore editing is builder/staff-shaped. Flagged. |
| `/tafk`, `/silentgive` | ToastedAFK staff tooling (`default: op`, not granted). Distinct from the player `/afk`. |
| `//wand`, `//set`, brushes | FAWE `fawe.permpack.basic` is `default: op`, not granted. A legacy `wepif.yml` grant exists but is superseded by LuckPerms. |
| `/nexo` | Admin/dev tooling only. |
| `/customdiscs`, mc-DiscordLink commands | Registered dynamically; exact syntax unverified. **Low confidence — needs in-game check before publishing.** |
| `/report` | **No such command exists** on this server — LiteBans' `plugin.yml` declares no `report` command, and nothing else registers one. Previously assumed; corrected. |
| All `adminvote*`, `/lp`, `/co`, `/litebans`, `/maintenance`, `/chunky`, `/scs`, `/parea`, `/setwarp`, `/setworth`, `/mythictools`, `/voidspawn`, `/ajleaderboards`, `/tab` (admin subcommands) | `default: op`, not granted to `default`. |

---

## Wiki corrections applied this pass

| Change | Detail |
|---|---|
| **REMOVED** | `/envoys` — plugin crashes on enable |
| **REMOVED** | `/v` alias on `/vote` — never declared |
| **REMOVED** | `/leaderboards` alias — never declared |
| **REMOVED** | `/warps` alias — invalid `alias:` key in DonutWarp |
| **REMOVED** | `/bounties` alias — invalid `alias:` key in DonutBounty |
| **CORRECTED** | `/gkits` → `/gkit` primary (aliases `/gkitz`, `/gkits`) |
| **CORRECTED** | View distance "up to 32" → flat **32 chunks** (ViewDistanceTweaks has no jar; scaling isn't running) |
| **ADDED** | `/seed`, `/back`, `/delhome`, `/renamehome`, `/tpahere`, `/tpacancel`, `/tpauto`, `/fastercrystals`, `/togglespawnmessages`, `/tab scoreboard`, `/list`, `/seen`, `/realname`, `/near`, `/getpos`, `/depth`, `/compass`, `/time`, `/itemdb`, `/suicide`, `/motd`, `/mail`, `/me`, `/nick`, `/ignore`, `/helpop`, `/crazyenchantments` alias |
| **ADDED** | `/tpdeny` alias `/tpno` |
