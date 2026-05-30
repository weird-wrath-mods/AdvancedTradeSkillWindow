# Advanced Trade Skill Window

A replacement for Blizzard's tradeskill window with better overview, sorting, searching, and a production queue. Works for all professions including enchanting.

This is the WotLK 3.3.5a build (v0.7.8), originally written 2006-2009 by Rene Schneider (Slarti on EU-Blackhand), with the additional fork changes listed below.

## Installation

Extract into your WoW directory so the folder lands in `Interface/AddOns/AdvancedTradeSkillWindow`, then enable it at the character screen. Open any tradeskill as normal and ATSW replaces the standard window.

## Commands

- `/atsw enable` / `/atsw disable`: turn ATSW on or off for the currently open tradeskill. Hold SHIFT while clicking a tradeskill icon to override per-open.
- `/atsw reagents`: open the all-characters reagent window for every saved queue, with a button to fetch needed reagents from your bank.
- `/atsw deletequeues`: delete all saved queues.

## Features

- Larger recipe list with sorting by group, name, difficulty, or a custom order you define.
- Production queue that auto-resolves intermediate crafts: queue an item and ATSW queues the sub-items it needs as reagents.
- Reagents window showing how many of each reagent you have in inventory, bank, and on alts, plus what a merchant sells. Auto-buy from merchants is supported.
- Shopping list at the auction house covering all saved queues.
- Shift-click an item with the chat line open to paste its reagent list into chat.

### Search

Type text to filter recipes by name, or combine these parameters:

| Parameter | Effect |
|---|---|
| `:reagent [name]` | recipes using that reagent |
| `:minlevel [n]` / `:maxlevel [n]` | by required item level |
| `:minrarity [grey/white/green/blue/purple]` / `:maxrarity [...]` | by item rarity |
| `:minpossible [n]` / `:maxpossible [n]` | by how many you can make from inventory |
| `:minpossibletotal [n]` / `:maxpossibletotal [n]` | as above, also counting bank, alts, and buyable mats |

Example: `leather :minlevel 20 :minrarity green`

## Fork changes (3.3.5a)

- **aux integration**: when aux is loaded the shopping list docks to the bottom of the aux window, and clicking a reagent runs an exact-name search in aux's Search tab. Falls back to the Blizzard browse when aux is absent. aux is an optional dependency.
- **Variable-yield materials**: shopping counts account for crafts that produce a range. A Pygmy Suckerfish makes 1-2 Pygmy Oil, so 30 oil is costed at about 20 fish, not 30.
- **Craft timer**: while crafting, the Process Queue button shows the remaining time for the current item.

## Compatibility

ATSW replaces the tradeskill window rather than adding to it, so some other tradeskill addons will not apply. It is explicitly compatible with ArmorCraft, LS3D craft info, and Fizzwidgets ReagentCost.

## Credits

Original addon by Rene Schneider. 3.3.5a baseline from the [locus313 WoW-3.3.5a-Addons](https://github.com/locus313/WoW-3.3.5a-Addons) collection. See `README.txt` for the original author's full changelog through v0.7.8.
