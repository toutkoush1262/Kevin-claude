# Mushroom Survivors

A small Vampire Survivors–style game: you are a mushroom, and every hungry creature in the forest wants to eat you. Open `index.html` in a browser; no build step needed.

- **Move:** WASD / arrow keys, or drag on touch screens. **Pause:** P / Esc.
- Spells fire automatically. Collect glowing spores to level up and choose upgrades.
- Hungry enemies: slugs, bats, goblins (with forks), truffle boars, pixies and trolls (with spoons); they get tougher over time. A ring of slugs is already on screen when a run starts.
- Spores: green ×1, pink ×2 and golden ×5 of an enemy's XP, which grows with how tough enemies have become; pink and golden get more common the longer you survive. XP per level keeps the first five levels as before, then grows gently.
- Passives Hungry Hyphae (+10% XP per level) and Geode Sense (+15% crystal drops per level) go to level 10.
- Magic mushrooms: red heals, blue gives a speed boost, gold pulls in every spore.
- Elites: from 10:00, crowned mini-bosses appear about every 60-90 seconds (at most 2 at once, none during the boss): the Truffle Tusker charges down a marked lane, the Goblin Chef throws a fan of cleavers after flashing aim lines, and the Troll Stomper leaps onto a marked circle. They drop pink spores and a blue or green crystal that doesn't count against the shop budget.
- Boss: at 20:00 the Giant Hippie arrives. He walks you down and bites, and between walks uses three telegraphed attacks you can dodge: Groovy Slam (a marked circle he leaps onto), Peace Waves (rings of slow peace signs with gaps) and Munchie Dash (a charge down a marked lane). Beating him drops golden spores plus a red and a purple crystal.
- Forage: every 5 mushrooms of one color levels that color up (max 5), offering 3 random enhancements from a pool (generic ones like Bountiful or Crystal Cap, plus ones unique to each color). Picks can repeat and stack. Mushrooms get rarer as a run goes on.
- Every level-up heals 5% of your max HP.
- Skills level up to 15. At skill levels 5, 10 and 15, pick a permanent modifier that changes how the skill behaves; modifiers branch, so your level 5 pick decides the level 10 options, and that pick decides the level 15 options (e.g. Mycelium Tendrils: Taproot for one big hit, or Fungal Web for more, weaker splits).
- Propagate grows clones of you that use your skills; its modifiers turn them into exploding decoys or a protective colony.
- Enemies drop colored crystals. Each 10-level shop cycle has a crystal budget (8 before the first shop, +1 per shop after, scaled by Geode Sense); trolls have a 2% red and 2% purple chance outside the budget. Every 10 player levels, Old Toadley the crystal merchant appears and waits until you visit; walk into him to spend crystals: blue levels an active skill and green a passive skill (each costs the new level number in crystals, so 5 → 6 costs 6). Red and purple crystals (rare troll drops) unlock extra skill slots: purple for active slots, red for passive slots.

## Versions

- **v0.0.5 — Rainbow update.** The rare rainbow **Mushroom Shield** grows a tree that fires rings of mushrooms and blocks all damage for 10 seconds. **Propagate** is now free for everyone at player level 10 (no slot): each clone copies one skill from your bar at 50% strength, and it levels up and picks modifiers at 20, 30 and 40 (Auntie no longer touches it). **Turbo snails** with shells and telegraphed dashes replace slugs from 10:00; slugs and bats thin out from 3:00; trolls can't be knocked back but back off after biting; spawning eases off once 150 enemies are out. Deaths are easier to read: red damage numbers, a low-health warning, a draining health bar, **Last Gasp** (once a minute a killing blow leaves you at 1 HP), and a last-hits recap in run logs. Also +2 max HP per level, 15% fewer early spawns, and Transplant Trauma blasts every 10 seconds.
- **v0.0.4 — Augment update.** Once any skill reaches level 15, Auntie Amanita appears near Old Toadley every time he does (with an arrow when she's off screen) and sells three augments per maxed skill for 20, 40, then 60 crystals (blue for actives, green for passives). New active skill **Shroomerang** throws spinning caps that fly out and back, hitting on both trips, with its own modifier tree and augments; a 7th active slot costs 4 purple. XP now follows a steeper curve fitted to real logged runs (total XP to level L is 0.227 × L^3.24, with early levels discounted), so a strong all-buffs run tops out near level 100 at 20:00. Enemy health eases in over minutes 3-8. Propagate's Transplant Trauma blasts cover the whole screen every 10 seconds and scale with the skill's level.
- **v0.0.3 — Skill slot update.** You can hold 4 active and 4 passive skills. Unlock more in Old Toadley's shop: active slots cost purple crystals (2, then 3), passive slots cost red crystals (2, 3, then 4). Red and purple can no longer be spent on skill levels. A skill bar at the bottom of the screen shows your slotted skills, their levels and cooldowns.
- **v0.0.2 — Forage update.** Magic mushrooms level up: every 5 of a color gives that color a Forage level (max 5) with a choice of stackable enhancements. Each color spawns on its own timer and gets rarer as a run goes on.
- **v0.0.1** — Everything before Forage: six active skills with branching modifiers at levels 5/10/15, passives, crystals and Old Toadley's shop, pink and golden spores, and the tuned XP curve.

Each version is a git tag (`v0.0.1` to `v0.0.5`); check one out to play that build.

## Test realm

`test.html` is a separate build for trying big changes before they reach the main game (`index.html`). It has a 🧪 Test button with shortcuts (max a skill, add crystals, summon the shop, jump to 10:00 or 19:50, invincibility). Currently testing on top of v0.0.5:

- **Active skill cap.** You start with 3 active skill slots and can unlock 2 more (2, then 4 purple crystals), for a maximum of 5. Propagate still doesn't use a slot. Passive slots are unchanged (4, up to 7).
- **Magic mushrooms from kills can be any color.** The 0.5% kill drop used to be red only; now it picks red, blue or golden at random, so blue and golden Forage level up about as fast as red. The rainbow Mushroom Shield now appears every 3-4.5 minutes all run instead of getting rarer.
- **Charms replace skill levels in Old Toadley's shop.** He now sells skill slots and charms: unique items you keep for the run, each bought once. Every visit he stocks 2 common charms (8 blue or 8 green), 1 rare (2 purple) and 1 corrupted (2 red, strong but with a downside). The current 14 charms are placeholders (damage, HP, speed, XP, pickup range, regen, damage taken).
- **Augments and Growth on level-ups.** Once a skill is maxed, one of its remaining augments can show up as a free level-up choice (Auntie still sells them). When there aren't 3 skills or augments left to offer, the empty spots fill with small repeatable Growth boosts: +4% damage, +10 max HP, +3% speed, +10% pickup range, or a 30% heal.
- **Pause button** in the bottom-right corner (P or Escape still work).
- **Beating the Giant Hippie wins the run.** A couple of seconds after the boss falls the run ends with a victory screen, and the log records it as won.
- **Weaker XP charms:** Lucky Pebble +5%, Golden Gills +12%, Gluttony +18% (it still makes you take 20% more damage).
- **Tougher late game.** From 10:00 enemy health climbs an extra amount, reaching 2x by 20:00 (elites too), and the Giant Hippie has 628,000 health (4x the old 157,000).
- **Feeding frenzies.** From 8:00, every 80-120 seconds all regular enemies move 45% faster for 15 seconds, with a banner, a timer and an orange glow at the screen edges. None during the boss fight.
- **More turbo snails:** up to 5 at a time, one every 6-10 seconds from 10:00.
- **Slower Propagate milestones.** It still arrives at player level 10, but levels up and picks its modifiers at 30, 50 and 75 instead of 20, 30 and 40, so the last one lands around 15:00.
- **No point-blank shotgunning.** Projectiles fired from inside an enemy (standing in the boss) only hit it once per burst, volley or throw; anything fired from outside works as before.
- **Bosses and elites hit relative to your health.** Every big-enemy hit deals at least a share of your max HP: boss bite 25%, slam 40%, charge 35%, ring shots 12%; elite bites 12%, Tusker charge 22%, Chef cleavers 8%, Stomper slam 25%. Touching them hurts in every state except mid-leap or mid-charge, so you can't stand inside them.
- **Skipping Old Toadley doesn't cost later shops.** If he's still waiting when the next 10 levels come around, he restocks his charms and announces himself again.
- **Arrows around the player.** Pointers to off-screen points of interest (boss, elites, Old Toadley, Auntie, rare crystals) sit in a ring right around your mushroom instead of at the screen edges. Propagate's milestone message floats over your mushroom so it no longer hides Old Toadley's arrival banner.
- **Run logs save reliably.** They save when the boss arrives, when you beat it and when you leave the page. Each save is a snapshot queued per run, so a slow save can't be dropped or mixed up with the next run when you press Play again. The end screen says "Run saved ✓" once it's safe to close.
