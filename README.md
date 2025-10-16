# TruthOrDarePlus Plugin for Minecraft 1.21 PaperMC

A fun Truth or Dare plugin for Minecraft servers with automated prompts, GUI menus, challenges, tiered rewards, and customizable timers! Perfect for multiplayer servers looking to add interactive chaos.

---

## Features

* **Automated Prompts**: Players receive Truth or Dare prompts at a configurable interval (default: 5 minutes).
* **Interactive GUI Menu**: Clean interface to choose between Truth (green book) or Dare (red totem).
* **50+ Truth Questions**: Random funny or quirky questions.
* **50+ Dare Challenges**: Random challenges with a 50% success/failure chance.
* **Tiered Reward System**:

  * **Tier 1 (85%)**: Common items (cobblestone, iron tools, food)
  * **Tier 2 (10%)**: Uncommon items (diamond/netherite armor, obsidian)
  * **Tier 3 (5%)**: Rare items (elytra, totems, end crystals)
* **Special LapisPearl Rewards**:

  * 1st dare: Mace of Wind Burst + 32 Wind Charges
  * 2nd dare: Full Netherite Armor Set
  * 3rd dare: Totem of Undying
  * 7th dare: Legendary Knockback Shovel (Knockback 255)
  * 25% chance for permanent extra hearts (max 20 hearts)
* **Failure Penalties**: Failed dares remove a random item from inventory.
* **Customizable Timer Interval** (v1.1.0): Change prompt frequency in-game or via config.
* **Admin Commands**: Set timer interval, reload configuration, and check current interval.
* **Persistent Settings**: Timer interval and other settings are saved across restarts.

---

## Installation

### Requirements

* Minecraft Server 1.21+
* PaperMC 1.21+ (or any Paper fork)
* Java 21+

### Steps

1. **Download the plugin**: `truthordare-1.1.0.jar`
2. **Install on server**: Place JAR in `plugins/` folder.
3. **Restart your server** (or run `/reload`, but restart recommended).
4. **Verify installation**: Check server logs for:

```
[TruthOrDarePlus] TruthOrDarePlus enabled!
```

---

## Commands

### For All Players

* `/truthordare` or `/tod` – Show plugin information and available commands
* `/truthordare getinterval` – Display current timer interval

### For Admins (`truthordare.admin` permission required)

* `/truthordare setinterval <minutes>` – Set the timer interval (min 1 minute)

  * Example: `/truthordare setinterval 10`
* `/truthordare reload` – Reload configuration after manual edits

---

## Configuration File

`plugins/TruthOrDarePlus/config.yml`:

```yaml
# TruthOrDarePlus Configuration File
# Timer interval in minutes (default: 5 minutes)
timer-interval-minutes: 5
```

* Edit manually and use `/truthordare reload`
* Or use in-game command `/truthordare setinterval`

---

## Permissions

* `truthordare.use` – Basic plugin access (default: everyone)
* `truthordare.admin` – Admin commands (default: ops only)

Example using LuckPerms:

```
/lp group admin permission set truthordare.admin true
```

---

## How It Works

1. **Prompt**: Players get a message:

```
[TruthOrDare] It's time! Choose Truth or Dare.
```

2. **Open GUI**: Menu opens automatically with Truth (green book) and Dare (red totem).
3. **Choose**:

   * **Truth**: Receive a random funny question to answer in chat
   * **Dare**: Get a random challenge with 50% success chance
4. **Results**:

   * **Success**: Reward from the tiered loot table
   * **Failure**: Lose a random item

---

## Examples

### Change Timer to 3 Minutes

```
/truthordare setinterval 3
```

### Check Current Interval

```
/truthordare getinterval
```

### Reload Config After Manual Edit

```
/truthordare reload
```

---

## Technical Details

* **Version**: 1.1.0
* **API**: Paper/Spigot 1.21+
* **Java**: 21+
* **Main Class**: `com.example.truthordare.TruthOrDarePlus`
* **Default Timer**: 5 minutes (6000 ticks)
* **Scheduler**: Bukkit task scheduler (runs every X ticks based on interval)
* **File Structure**:

```
src/main/java/com/example/truthordare/
├── TruthOrDarePlus.java           # Main plugin class
├── TruthOrDarePlusGUI.java        # GUI menu handler
├── TruthOrDarePlusTruths.java     # Truth questions
├── TruthOrDarePlusDares.java      # Dare challenges
├── TruthOrDarePlusRewards.java    # Tiered rewards system
├── TruthOrDarePlusLapisPearl.java # Special player rewards
└── TruthOrDarePlusFailure.java    # Failure penalties
```

---

## Troubleshooting

* **Timer not working after restart?**

  * Ensure `config.yml` exists in `plugins/TruthOrDarePlus/`
  * Timer interval must be ≥1 minute
  * Check server logs for errors

* **Can't use admin commands?**

  * Verify `truthordare.admin` permission
  * Ops should have it by default

* **Want original 5-minute timer?**

  * Use `/truthordare setinterval 5`
  * Or delete `config.yml` and reload

---

## Support

* Check server console logs for errors
* Ensure Paper/Spigot version is 1.21+
* Ensure Java 21+ is installed

---

**Enjoy Truth or Dare fun on your Minecraft server!** 🎮
