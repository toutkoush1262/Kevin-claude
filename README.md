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

- **v0.0.3 — Skill slot update.** You can hold 4 active and 4 passive skills. Unlock more in Old Toadley's shop: active slots cost purple crystals (2, then 3), passive slots cost red crystals (2, 3, then 4). Red and purple can no longer be spent on skill levels. A skill bar at the bottom of the screen shows your slotted skills, their levels and cooldowns.
- **v0.0.2 — Forage update.** Magic mushrooms level up: every 5 of a color gives that color a Forage level (max 5) with a choice of stackable enhancements. Each color spawns on its own timer and gets rarer as a run goes on.
- **v0.0.1** — Everything before Forage: six active skills with branching modifiers at levels 5/10/15, passives, crystals and Old Toadley's shop, pink and golden spores, and the tuned XP curve.

Each version is a git tag (`v0.0.1`, `v0.0.2`, `v0.0.3`); check one out to play that build.

## Test realm

`test.html` is a separate build for trying big changes before they reach the main game (`index.html`). It has a 🧪 Test button with shortcuts (max a skill, add crystals, summon the shop, jump to 10:00 or 19:50, invincibility).

Currently testing **v0.0.4-test — Auntie Amanita & augments**: once any skill reaches level 15, Auntie Amanita appears near Old Toadley every time he does (with an arrow when she's off screen). She sells three augments for each maxed skill, in any order, for 20, 40, then 60 crystals: blue for active skills, green for passives.

Also testing **Shroomerang**, a new active skill: it throws spinning mushroom caps that slow near the far end, turn around and fly back to you, hitting enemies on both trips. Up to 4 caps per throw at level 15, with its own modifier tree and augments. The test realm also allows a 7th active slot (4 purple), since there are now 7 active skills.

Also testing a **steeper XP curve fitted to a real logged run**: total XP to reach level L is 0.161 × L⁴, which would have paced that run at about level 28 at 10:00 and 45 at 20:00 (it actually reached 74 at 10:00 on the old curve).
