# ShinyVale Plugin Audit

**Audit date:** 2026-08-21
**Server:** Luminol `1.21.11-DEV-ver/1.21.11@e5ff8df` (Folia fork), Minecraft 1.21.11, API `1.21.11-R0.1-SNAPSHOT`, Java 21

**Method:** every jar in `plugins/*.jar` had its `plugin.yml` / `paper-plugin.yml` extracted programmatically; results cross-referenced against the startup log (`logs/2026-08-16-2.log.gz`), each plugin's active config, and the LuckPerms `default` group (`plugins/LuckPerms/yaml-storage/groups/default.yml`).

> **Rule applied throughout:** installed jar + current config + runtime evidence beats external documentation. Where they disagreed, the server won.

---

## 1. Plugin inventory

### 1a. Jars present but **NOT running** — do not document

| Plugin | Jar | Evidence | Impact |
|---|---|---|---|
| **CrazyEnvoys 1.13.0** | `CrazyEnvoys-1.13.0.jar` | Startup log: `Error occurred while enabling CrazyEnvoys v1.13.0 (Is it up to date?)` followed by a Luminol `TickThread` "Thread failed main thread check: Async chunk retrieval" stack trace. Loads, then **fails during enable**. | `/envoys`, `/envoy`, `/crazyenvoys` **do not work**. Removed from wiki. |
| **HeadDB 6.0.0-rc.2** | `HeadDB-6.0.0-rc.2.jar` | Startup log: `Could not load plugin 'HeadDB v6.0.0-rc.2' as it is not marked as supporting Folia!` | Never loads. `/headdb`, `/hdb` unavailable. |
| **Shopkeepers 2.23.10** | `Shopkeepers-2.23.10.jar` | Startup log: `Could not load plugin 'Shopkeepers v2.23.10' as it is not marked as supporting Folia!` | Never loads. Villager player-shops **do not exist** on this server. Correctly excluded from wiki. |

### 1b. Config folders with **no jar at all** — legacy only

`Towny`, `BetterTeams`, `JustDuel`, `ZelDuels`, `PvPManager`, `DonutCombatLog` (jar found relocated into `plugins/bStats/`, outside the load path), **`ViewDistanceTweaks`**.

> **ViewDistanceTweaks is significant:** its config declares dynamic view-distance scaling (22–32). With no jar, that scaling **is not running** — view distance is the flat `view-distance=32` from `server.properties`. Wiki corrected from "up to 32" to a flat "32 chunks".

### 1c. Active plugins

85 plugins confirmed `Enabling` in the startup log. Player-facing ones are profiled below; libraries (CommandAPI, packetevents, ProtocolLib, MCKotlin-Paper, lavaplayer-lib, Vault, PlaceholderAPI, DonutDatabase, spark, ViaVersion/ViaBackwards) and pure-admin plugins (LuckPerms, LiteBans, CoreProtect, Maintenance, Chunky, AxInventoryRestore, WorldGuard, FAWE, ItemEdit, UltimateAutoRestart, AIChatModeration, zSchedulers, AdvancedServerList, TAB, DiscordSRV) are excluded from player docs by design.

---

## 2. Identity + documentation confidence

| Plugin | Version | Identity confirmed via | Docs source | Confidence |
|---|---|---|---|---|
| SimpleClaimSystem | 1.12.3.3 | `plugin.yml` main `fr.xyness.SCS.SimpleClaimSystem`, author Xyness | Own `plugin.yml` + `langs/en_US.yml` in-game help strings + `config.yml` | HIGH |
| Duels (Duels-Optimised) | 7.6 | main `com.meteordevelopments.duels.DuelsPlugin`, authors Realized/DUMBO | Own `plugin.yml` + `commands.yml` + `config.yml` | HIGH |
| EssentialsX | 2.22.0-dev+69-675b801-**Folia** | `plugin.yml` name `Essentials` | Own `plugin.yml` + `config.yml` `player-commands:` whitelist | HIGH — note this is a **Folia dev fork**, not an upstream release |
| QuickShop-Hikari | 6.2.0.11 | `plugin.yml` | Own `plugin.yml` + `config.yml` | HIGH |
| CrazyAuctions | 1.7.0 | `plugin.yml` | Own `plugin.yml` + `config.yml` | HIGH |
| BetterRTP | 3.6.13 | `plugin.yml` | Own `plugin.yml` + `config.yml` | HIGH |
| VotingPlugin | 6.19 | main `com.bencodez.votingplugin.VotingPluginMain` | Own `plugin.yml` | HIGH — plugin self-reports a newer 7.1.1 exists; **6.19 is authoritative here** |
| SmartSpawner | 1.5.3 | `plugin.yml` | Own `plugin.yml` + `config.yml` + `mob_drops.yml` + `item_prices.yml` | HIGH |
| GSit | 3.1.0 | `plugin.yml` | Own `plugin.yml` | HIGH |
| CrazyEnchantments | 2.7.2 | `plugin.yml` | Own `plugin.yml` | HIGH |
| EnhancedPay | 2.3 | `plugin.yml` | Own `plugin.yml` | HIGH |
| Worlds | 3.10.5 | `paper-plugin.yml`, author NonSwag, thenextlvl.net | Own `paper-plugin.yml` | HIGH |
| FasterCrystals | 2.1.0 | jar `pvpclub-FasterCrystals-2.1.0.jar` | Own `plugin.yml` | HIGH |
| **Donut\* suite** (Bounty, Homes, TP, Warp, Shop, Worth, Order, Settings, Teams, Ping, Nightvision, Phantoms, FindPlayer, CrateCore, CrateSystem, Keyall, HoverStats, RTPZone, Fly, MythicTools, CustomCommands) | various | `plugin.yml` only | **No external docs exist** — private/custom plugins | MEDIUM — derived entirely from jar metadata + configs + runtime |
| AxPlayerWarps / AxTrade / AxGraves / AxCalendar | 1.12.0 / 1.21.0 / 1.28.0 / 2.6.0 | `plugin.yml` | Own configs (**no `commands:` block — registered dynamically**) | MEDIUM |
| SkinsRestorer | 15.12.5 | `plugin.yml` | Own permissions (**no `commands:` block — dynamic**) | MEDIUM |
| Nexo | 1.21 | `plugin.yml` | Own configs (**dynamic commands**) | MEDIUM — admin-only, deliberately not in player wiki |
| CustomDiscs | 2.5.1 | `plugin.yml` | Own config (**dynamic, CommandAPI**) | LOW — exact syntax unverified, **not published** |
| mc-DiscordLink | 2.8.1 | main `com.mongenscave.discordlink`, author kxtsoo | `plugin.yml` has **no commands block** | LOW — command names unverified, **not published** |

---

## 3. The `default` group — what players actually have

Source: `plugins/LuckPerms/yaml-storage/groups/default.yml` (LuckPerms storage is **`yaml`**, per `config.yml` → `storage-method: yaml`; the `luckperms-h2-v2.mv.db` file is a stale artifact and is **not** the live data).

**Granted (abridged to player-relevant):** `scs.command.claim.*`, `scs.command.claim.{add,merge,remove,setname,settings}`, `duels.*`, `gsit.*`, `crazyenchantments.player.*` + `.gui/.tinker/.blacksmith/.limit.5/.base-limit.3`, `skinsrestorer.command.*`, `axplayerwarps.{create,help,use,warps.20}`, `crazyauctions.{access,view,sell,sell.10000}`, `epay.use`, `essentials.{afk,afk.auto,msg,reply,spawn,tpa,tpacancel,tpaccept,tpahere,joinfullserver}`, `home.{default,use}`, `homes.default`, `leaderboardmaker.use`, `order.default`, `quickshop.{create.*,currency,find,preview,shopnaming,staff}`, `voicechat.{groups,listen,speak}`, `votingplugin.commands.vote.gui`, `minecraft.command.seed`, `worlds.command.seed`, `fastercrystals.toggle`, `tab.scoreboard{,.show,.toggle}`, `zinvisitemframes.{craft,craft.item_frame,craft.glow_item_frame,place}`, `discordlink.{link,unlink,profile,player.help,boostrewards}`.

**Explicitly DENIED (`value: false`) — must never appear as player commands:**
`essentials.fly`, `flyformvps`, `crazyauctions.bid`, `bukkit.*`, `bukkit.command.*`, `bukkit.command.{help,plugins,tps,version}`, `minecraft.command.spawnpoint`, `zelduels.{use,queue,spectate}`.

**Vestigial grants for plugins that no longer exist** (harmless, ignore): `justduel.use`, `infinitejump.use`, `customenderchest.level.5`, `interactivebooks.open.updates`, `chatmanager.message`, `leaderboardmenus.user*`, `easycommandblocker.tab.default`.

---

## 4. Known unresolved items

| Item | Why unresolved |
|---|---|
| `/rules` ownership | DeluxeMenus `rules.yml` declares `open_command: rules` but **lacks `register_command: true`**; Essentials **also** whitelists `rules` in `player-commands`, and its `rules.txt` is **empty**. Which wins is load-order dependent and not statically determinable. **Worth testing in-game** — if `/rules` shows nothing, Essentials is winning and `register_command: true` should be added to `rules.yml`. |
| `/spawn`, `/afk` ownership | Same collision pattern (EssentialsX/EssentialsXSpawn vs. DeluxeMenus menus that *do* set `register_command: true`, plus ToastedAFK). Player-visible behavior is equivalent either way, so both are documented generically. |
| `/warps`, `/bounties` aliases | DonutWarp and DonutBounty declare these under the key **`alias:`** (singular) — not the valid Bukkit key `aliases:`. Bukkit ignores unknown keys, so these aliases most likely **never register**. Removed from wiki as aliases; base commands `/warp` and `/bounty` are unaffected. |
| 30,000,000 × 30,000,000 world border | Stored as binary NBT in the world's `level.dat`; no plain-text config to verify against. **No contradicting evidence found.** Confirm in-game with `/worldborder get`. |
| `duels.*` and `gsit.*` wildcard grants | Both cascade into normally-op-only nodes (`duels.admin` → `duels.stats.others`, `duels.kits.*`, `duels.teleport.bypass`, `duels.spectate.anonymously`; `gsit.*` → `GSit.Reload`, `GSit.Kick.*`). Functionally live today but almost certainly unintentional. **Not published as player features.** Recommend narrowing these grants. |

---

## 5. Reproducing this audit

```powershell
# 1. Dump every jar's plugin.yml
Add-Type -AssemblyName System.IO.Compression.FileSystem
foreach ($jar in Get-ChildItem "plugins\*.jar") {
  $zip = [System.IO.Compression.ZipFile]::OpenRead($jar.FullName)
  $e = $zip.Entries | Where-Object { $_.FullName -in @("plugin.yml","paper-plugin.yml") } | Select-Object -First 1
  if ($e) { (New-Object System.IO.StreamReader($e.Open())).ReadToEnd() }
  $zip.Dispose()
}

# 2. Confirm what actually loaded (a jar existing proves nothing)
Select-String -Path "logs\latest.log" -Pattern "Enabling |Error occurred while enabling|not marked as supporting Folia"

# 3. Read the real permission source
Get-Content "plugins\LuckPerms\yaml-storage\groups\default.yml"
```
