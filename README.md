# TruthOrDarePlus Plugin for Minecraft 1.21 PaperMC

A fun Truth or Dare plugin for Minecraft servers with automated prompts, GUI menus, challenges, and tiered rewards!

## Features

- **Automated Prompts**: Every 5 minutes, all players receive a Truth or Dare prompt
- **Interactive GUI Menu**: Clean menu interface to choose between Truth or Dare
- **50+ Truth Questions**: Random funny questions for players to answer
- **50+ Dare Challenges**: Fun challenges with random success/failure
- **Tiered Reward System**:
  - Tier 1 (85%): Common items (cobblestone, iron tools, food)
  - Tier 2 (10%): Uncommon items (diamond/netherite armor, obsidian)
  - Tier 3 (5%): Rare items (elytra, totems, end crystals)
- **Special LapisPearl Rewards**: Progressive rewards for player "LapisPearl"
  - 1st dare: Mace of Wind Burst + 32 Wind Charges
  - 2nd dare: Full Netherite Armor Set
  - 3rd dare: Totem of Undying
  - 7th dare: Legendary Knockback Shovel (Knockback 255)
  - 25% chance for permanent extra hearts (max 20 hearts)
- **Failure Penalties**: Failed dares remove a random item from inventory

## Installation

### Requirements
- Minecraft Server 1.21+
- PaperMC 1.21+ (or any Paper fork)
- Java 21+

### Steps

1. **Download the plugin JAR**:
   - The compiled plugin is located at: `target/truthordare-1.0.0.jar`

2. **Install on your server**:
   - Copy `truthordare-1.0.0.jar` to your server's `plugins/` folder
   - Restart your server or run `/reload` (restart recommended)

3. **Verify installation**:
   - Check server logs for: `[TruthOrDarePlus] TruthOrDarePlus enabled!`
   - The plugin will automatically start prompting players every 5 minutes

## Building from Source

If you want to rebuild the plugin:

```bash
mvn clean package
```

The compiled JAR will be in `target/truthordare-1.0.0.jar`

## How It Works

### For Players

1. **Receive Prompt**: Every 5 minutes, you'll get a message: `[TruthOrDare] It's time! Choose Truth or Dare.`
2. **Open GUI**: A menu automatically opens with Truth (green book) and Dare (red totem)
3. **Choose**:
   - **Truth**: Receive a random funny question to answer in chat
   - **Dare**: Get a random challenge with 50% success chance
4. **Results**:
   - **Success**: Receive a reward from the tiered loot table
   - **Failure**: Lose a random item from your inventory

## Technical Details

- **API Version**: 1.21
- **Main Class**: `com.example.truthordare.TruthOrDarePlus`
- **Event Handling**: Inventory click events for GUI interaction
- **Scheduler**: Bukkit task scheduler (runs every 6000 ticks = 5 minutes)

## File Structure

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

## Customization

To customize the plugin, edit the source files:

- **Change timer interval**: Edit line 32 in `TruthOrDarePlus.java` (6000 ticks = 5 minutes)
- **Add truths**: Edit the list in `TruthOrDarePlusTruths.java`
- **Add dares**: Edit the list in `TruthOrDarePlusDares.java`
- **Modify rewards**: Edit the tier lists in `TruthOrDarePlusRewards.java`
- **Change LapisPearl name**: Edit line 58 in `TruthOrDarePlusDares.java`

After making changes, rebuild with `mvn clean package`

## License

This plugin is provided as-is for use on your Minecraft server.

## Support

For issues or questions about this plugin, check the server logs for error messages.

---

**Enjoy the Truth or Dare fun on your server!** 🎮
