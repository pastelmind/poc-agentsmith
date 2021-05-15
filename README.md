# PoC: Agent Smith

This project is a proof-of-concept that demonstrates the effect of a bug<sup>\[1\]</sup> in KoLmafia. It contains a bunch of files inside the `relay/agentsmith_jail/` directory.

When installed with the `svn checkout` command, this project will overwrite numerous files in your `relay/` and `scripts/` directories with files from `relay/agentsmith_jail/`. Agent Smith has escaped containment.😎

\[1\] Or an unintended side effect of a feature.

## How to test

1. ⚠ **Back up your KoLmafia directory.** Copy it somewhere safe, so you can restore it afterwards. You have been warned.
2. Run `svn checkout https://github.com/pastelmind/poc-agentsmith/trunk/release`
3. If you see a massive popup asking "Svn checkout wants to overwrite local files", click "Yes". After all, all the files are in `relay/agentsmith_jail/`. Surely, they can't do anything.\
   Note: If the popup is too large, you may not see the buttons. In this case, just hit the <kbd>Enter</kbd> key.
4. Watch as your ASH scripts, relay scripts, CSS stylesheets, JavaScript files, and other files are overwritten by Agent Smith.

## How does this work?

Whenever installing a new project with `svn checkout`, KoLmafia examines each file to decide how and where it should be placed. If the file being installed is under `relay/` or `scripts/`, it dives recursively into your current `relay/` and `scripts/` directories, searching for a file with the same name. If a match is found, it decides that the two files are the same, and overwrites the existing one with the new one, _even if the actual paths are different._

## Why does KoLmafia do this?

The exact details are lost to the sands of time, but I believe that it is there to allow users to move their scripts around (to better organize the Script Menu) _and_ still receive automatic updates via `svn update`. Since it compares file names, the automatic update would no longer work once you rename a script.

## What scripts are affected?

First, this overwrites KoLmafia's own files. It won't affect the KoLmafia UI, but it may cause glitches when using the relay browser.

Second, this overwrites almost every installable script available in the Script Manager. Here's an exhaustive list:

<details>
<summary>Click to expand/collapse</summary>

(The links point to the SVN/Git repositories; they won't work when you click it.)

- [Airport Colors](https://svn.code.sf.net/p/kol-airport-colors/code)
- [Arrrbor Day](https://svn.code.sf.net/p/veracity0/code/arrrbor-day/)
- [Ascension Checklist Handler](https://svn.code.sf.net/p/eodascensionchecklist/code/)
- [Asdon Martin GUI](https://github.com/Ezandora/Asdon-Martin-GUI/branches/Release/)
- [autoBasement](https://svn.code.sf.net/p/winterbay-mafia/autobasement/code/)
- [autoscend](https://github.com/Loathing-Associates-Scripting-Society/autoscend/trunk/RELEASE/)
- [Bale's Campground](https://svn.code.sf.net/p/bale/relay/code/campground/)
- [Bale's Mall](https://svn.code.sf.net/p/bale/relay/code/mall_storeLinks/)
- [Bale's Museum](https://svn.code.sf.net/p/bale/relay/code/museum/)
- [Bale's Topmenu](https://svn.code.sf.net/p/bale/relay/code/topmenu/)
- [Bastille](https://github.com/Ezandora/Bastille/branches/Release/)
- [BatBrain](https://svn.code.sf.net/p/batbrain/code/)
- [BatMan RE](https://svn.code.sf.net/p/batman-re/code/)
- [BestBetweenBattle](https://svn.code.sf.net/p/bestbetweenbattle/code/)
- [Bounty Hunter Helper](https://svn.code.sf.net/p/rlbond86-mafia-scripts/code/bounty_hunter_helper/trunk/)
- [Bounty](https://svn.code.sf.net/p/autobhh/code/)
- [Bumcheekcend](https://svn.code.sf.net/p/bumcheekascend/code/bumcheekascend/)
- [BumPork](https://svn.code.sf.net/p/bumcheekascend/code/bumpork/)
- [buttonFrenzy](https://svn.code.sf.net/p/guyymafia/code/buttonfrenzy/)
- [CanAdv](https://svn.code.sf.net/p/therazekolmafia/canadv/code/)
- [CartoucheHunter](https://svn.code.sf.net/p/cartouchehunter/svn/)
- [CFStat](https://svn.code.sf.net/p/kolmafiascripts/cfstat/code/)
- [Charsheet: Skills by Class](https://svn.code.sf.net/p/relay-charsheet/code/)
- [ChIT](https://svn.code.sf.net/p/mafiachit/code/)
- [Choice Override](https://github.com/Ezandora/Choice-Override/branches/Release/)
- [ckb's Iconic topmenu](https://svn.code.sf.net/p/ckbiconmenu/code/)
- [Clan Raidlog Parser](https://github.com/balefull/raidlog-parser/branches/master)
- [CLI Links](https://svn.code.sf.net/p/clilinks/code/)
- [CounterChecker](https://svn.code.sf.net/p/bale/counterchecker/code/)
- [Currencies](https://svn.code.sf.net/p/kolmafiascripts/currencies/code/)
- [DCQuest](https://svn.code.sf.net/p/kolmafiascripts/dcq/code/)
- [Dinsey Landfill](https://svn.code.sf.net/p/bale/dinsey/code/)
- [Drag-n-Drop Inventories](https://svn.code.sf.net/p/drag-n-drop-inventories/code)
- [DreadDrunk](https://svn.code.sf.net/p/guyymafia/code/dreaddrunk/)
- [EatDrink](https://svn.code.sf.net/p/therazekolmafia/eatdrink/code/)
- [Enhanced Inventory Spoilers](https://svn.code.sf.net/p/rlbond86-mafia-scripts/code/enhanced_inventory_spoilers/trunk/)
- [EoD Softcore Ascension Script](https://svn.code.sf.net/p/eodscascension/code-0/)
- [Excavator](https://github.com/gausie/excavator/trunk/RELEASE/)
- [extraction](https://svn.code.sf.net/p/digitrev/code/extraction)
- [FantasyRealm](https://github.com/Ezandora/FantasyRealm/branches/Release/)
- [Far Future](https://github.com/Ezandora/Far-Future/branches/Release/)
- [Fax Identification](https://svn.code.sf.net/p/rlbond86-mafia-scripts/code/fax_tell/trunk/)
- [Form of...HTML!](https://svn.code.sf.net/p/formhtml/code/)
- [Gain](https://github.com/Ezandora/Gain/branches/Release/)
- [Genie](https://github.com/Ezandora/Genie/branches/Release/)
- [Get Skill](https://svn.code.sf.net/p/therazekolmafia/getskill/code/)
- [Guide](https://github.com/Ezandora/Guide/branches/Release/)
- [Harvest](https://svn.code.sf.net/p/mafia-harvest/code/)
- [Helix Fossil](https://github.com/Ezandora/Helix-Fossil/branches/Release/)
- [Improved Guild Trainer](https://svn.code.sf.net/p/rlbond86-mafia-scripts/code/better_trainer/trunk/)
- [KGBriefcase](https://github.com/Ezandora/Briefcase/branches/Release/)
- [LootBot](https://svn.code.sf.net/p/guyymafia/code/lootbot/)
- [LT&T Office](https://svn.code.sf.net/p/bale/ltt/code/)
- [Make Meat Fast](https://svn.code.sf.net/p/winterbay-mafia/farm/code/)
- [Manage Store](https://svn.code.sf.net/p/kolmafiascripts/shop/code/)
- [Manor Informer](https://svn.code.sf.net/p/bale/relay/code/manor_unlockInfo/)
- [Mercenary Mood](https://svn.code.sf.net/p/mercenarymood/code)
- [Missing Manuel](https://svn.code.sf.net/p/missingmanuel/code/trunk/)
- [Modular Choice Override](https://svn.code.sf.net/p/rlbond86-mafia-scripts/code/modular_choice_override/trunk/)
- [Monster Manuel: Improved](https://svn.code.sf.net/p/bale/relay/code/Monster_Manuel_Improvement/)
- [Nemesis.ash](https://svn.code.sf.net/p/slyz-nemesis/code/)
- [New Life](https://svn.code.sf.net/p/bale/new-life/code/)
- [NewYou](https://github.com/coandco/mafia-NewYou/trunk/)
- [Noobsorb](https://svn.code.sf.net/p/kolm-noobsorb/svn/)
- [NS Tower Scroller](https://svn.code.sf.net/p/bale/ns-tower-relay/code/)
- [OBE Universal Recovery](https://svn.code.sf.net/p/mafiarecovery/code/)
- [OCD Inventory Control](https://svn.code.sf.net/p/bale/ocd/code/)
- [PandamoniumQuest](https://svn.code.sf.net/p/wrldwzrd89-mafia-scripts/code/trunk/pandamonium-quest/)
- [PirateRealm](https://github.com/Ezandora/PirateRealm/trunk/Release/)
- [Pizza Cube GUI](https://github.com/ggvgiu/PizzaCubeGUI/branches/Release)
- [Pork to the Future](https://svn.code.sf.net/p/guyymafia/code/porkfuture/)
- [Prefref Plus](https://svn.code.sf.net/p/reference-plus/code/)
- [Psychose-a-Matic](https://svn.code.sf.net/p/psychoseamatic/code/)
- [Relay Task List](https://svn.code.sf.net/p/rlbond86-mafia-scripts/code/task_list/trunk/)
- [Rollover Management](https://svn.code.sf.net/p/rollover-management/code/)
- [Skill Planner/CS Tracker](https://svn.code.sf.net/p/mafia-cs-planner/svn/)
- [SL_Ascend](https://github.com/soolar/sl_ascend/trunk/RELEASE/)
- [Slime Tube](https://svn.code.sf.net/p/slimetube/code/)
- [Slimecalc](https://svn.code.sf.net/p/guyymafia/code/slimecalc/)
- [SmartStasis](https://svn.code.sf.net/p/smartstasis/code/)
- [Snapshot Maker](https://svn.code.sf.net/p/ccascend/code/snapshot)
- [Snojo Training](https://svn.code.sf.net/p/bale/snojo/code/)
- [Source Terminal GUI](https://github.com/Ezandora/Source-Terminal-GUI/branches/Release/)
- [Space Tripper](https://svn.code.sf.net/p/guyymafia/code/spacetripper/)
- [Spacegate Sounds](https://svn.code.sf.net/p/veracity0/code/spacegate-sounds/)
- [Spacegate](https://github.com/Ezandora/Spacegate/branches/Release/)
- [Spelunky Reference](https://svn.code.sf.net/p/bale/spelunky/code/)
- [Standard Rollover Bonus](https://svn.code.sf.net/p/standard-rollover-bonus/code/)
- [Superdrinks for Fun and Profit](https://svn.code.sf.net/p/fluxxdog-coding/code/trunk/superdrinks/)
- [Superhuman Cocktail Maximizer](https://svn.code.sf.net/p/rlbond86-mafia-scripts/code/cocktailmax/trunk/)
- [Sushi](https://svn.code.sf.net/p/winterbay-mafia/sushi/code/)
- [Sweet Synthesis](https://github.com/Ezandora/Sweet-Synthesis/branches/Release/)
- [Tale Prank](https://svn.code.sf.net/p/guyymafia/code/taleprank/)
- [The Sea](https://svn.code.sf.net/p/therazekolmafia/thesea/code/)
- [Tower Checker](https://svn.code.sf.net/p/towerchecker/code/)
- [TrickTreat](https://svn.code.sf.net/p/guyymafia/code/tricktreat/)
- [TrophyTastic](https://svn.code.sf.net/p/guyymafia/code/trophytastic/)
- [UberPvPOptimizer](https://svn.code.sf.net/p/uberpvpoptimizer/svn/)
- [Universal Recovery](https://svn.code.sf.net/p/kolmafiascripts/mafiarecovery/code/)
- [Unlock Dreasylvania](https://svn.code.sf.net/p/unlock-dread2/code/)
- [vcon](https://svn.code.sf.net/p/veracity0/code/vcon/)
- [Veracity's BeachComber](https://svn.code.sf.net/p/veracity0/code/beach/)
- [Veracity's Garden Harvester](https://svn.code.sf.net/p/veracity0/code/garden/)
- [Veracity's Gingerbread City](https://svn.code.sf.net/p/veracity0/code/gingerbread/)
- [Veracity's Meat Farming](https://svn.code.sf.net/p/veracity0/code/meat-farm/)
- [Veracity's Spacegate](https://svn.code.sf.net/p/veracity0/code/spacegate/)
- [VotingBooth](https://github.com/Ezandora/Voting-Booth/trunk/Release/)
- [vprops](https://svn.code.sf.net/p/veracity0/code/vprops/)
- [WHAM](https://svn.code.sf.net/p/winterbay-mafia/wham/code/)
- [Wiki Links](https://svn.code.sf.net/p/bale/relay/code/desc_wikiLinks/)
- [Woods quest starter](https://svn.code.sf.net/p/bale/relay/code/woods_questStart/)
- [WTF Familiars](https://svn.code.sf.net/p/relaywtf/code/famswtf/)
- [WTF Inventory](https://svn.code.sf.net/p/relaywtf/code/inventorywtf/)
- [WTF Shops](https://svn.code.sf.net/p/relaywtf/code/shopwtf/)
- [WTF Skills](https://svn.code.sf.net/p/relaywtf/code/skillswtf/)
- [WTF VIP Lounge](https://svn.code.sf.net/p/relaywtf/code/vipwtf/)
- [Zap Wand](https://svn.code.sf.net/p/zap-wand/code/)
- [ZLib](https://svn.code.sf.net/p/zlib/code/)
</details>

## Is this a security problem? Are you a hacker?

Technically, no. It doesn't steal your login passwords, items, or meat. It doesn't compromise your computer.

This merely demonstrates that careless file naming can accidentally destroy other people's files.

## What can I do about it?

### If I am a script writer...

_Namespace your file names. Avoid common names._

For example, instead of `styles.css`, use `unique-project-name.styles.css`. Ensure that your file names would survive even if all of them are placed in the same directory.

Do not assume that your files are safe from being overwritten, just because you put them in a subdirectory.

### If I am a user...

In general, be careful about what scripts you install. **Don't blindly press Yes.**

If you discover that two projects are using the same file name, inform both authors so that they can reach an amicable agreement on who gets to use which file name.

## Finally...

We are [discussing this bug in the KoLmafia forums](https://kolmafia.us/threads/svn-update-does-not-move-files-in-local-copy.26043/). If you are interested in contributing to KoLmafia, please join in and keep the talk going.

## Trivia

While preparing this repo, I discovered that several projects in the Script Menu are already affected by this issue. For example, some projects use "common" names like `inventory.ash` within different subdirectories.
