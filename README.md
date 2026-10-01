# Cadw Raglan Castle — Code Builder tutorials

Guided Minecraft Education Code Builder (MakeCode) tutorials for the Raglan Castle journey on Cadw Galeri 3. Both run in the Blocks editor. The learning design, starter programs, Edward's Workshop Notebook pages and Notebook Observations come from Cadw's activity specifications (Q2C v3.2, Q2E v2.3). The Notebook pages are the steps, and the Observations are the hints.

## The activities

| File | Activity | Opened from | Chat command | Starter | The learner adds |
| --- | --- | --- | --- | --- | --- |
| `q2c-bells.md` | Q2C Edward's Bell Communication System | Technocamps Mentor, **Start Coding**, in the cellar workshop | `ring` | Teleports the Agent and sends the first S: three rings of Bell 1, returning to the start | Turn towards Bell 2, send O, return to Bell 1, send the final S. Optional: loops and a function |
| `q2e-gardener.md` | Q2E Edward's Mechanical Gardener | Technocamps Mentor, **Start Coding**, in the Terraced Gardens | `check` | Teleports the Agent, crosses one row (`repeat 9`) and turns into the next | A full lawnmower route with loops; `if` and Agent inspection for Wildflowers and Leaf Litter; the variables `wildFlower` and `leafLitter` (start at 0, change by 1); `say` for each count. Optional: Boolean OR with Rose Bushes |

## Open in Code Builder

The Mentor's **Start Coding** button runs `codebuilder navigate @s true <url>` with these exact URLs:

- Q2C: https://minecraft.makecode.com/?ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:github:BlockBuilderJoe/cadw-raglan-makecode/q2c-bells
- Q2E: https://minecraft.makecode.com/?ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:github:BlockBuilderJoe/cadw-raglan-makecode/q2e-gardener

When testing, add `skipgithubcache=1` after `?`. Never add a second `#branch` fragment: the default branch is what learners get.

## The world confirms success

The learner presses the green Play button, which registers the chat command, and then types `ring` or `check` in the Minecraft chat. The Raglan runtime on Galeri 3 watches the Agent, not the code. The tutorials never announce success themselves (`@hideDone`), and they never ask the learner to add code that reports its own success.

- **Q2C.** The Agent starts at 8623 7 16941, facing north. Bell 1's plate is one block ahead (Z16940) and Bell 2's is one block behind (Z16942). Bell 3 (Z16944) is not part of the S–O–S. A ring counts only when the Agent, not the player, presses the plate. The world passes Bell 1 ×3, Bell 2 ×3, Bell 1 ×3 and says "The bells sent S-O-S. Speak to Owain." A wrong run names the first ring that differs.
- **Q2E.** The Agent starts at 8521 -1 16945, facing north (−Z). The bottom-left corner is a 12 × 12 area of clear cells (X8521–8532, Z16934–16945) with an oak fence outside it. The world passes a route that covers every cell and never leaves the garden, then says "The Mechanical Gardener covered the whole garden. Speak to Owain." It cannot read `say`, so the counts are for the learner.

## Format rules

- Metadata is `### @hideDone true`. Keep step controls visible: `@hideIteration true` hides Previous/Next and the step counter, trapping these multi-step lessons at Predict. `lockedEditor=1` keeps the learner in the tutorial and `@hideDone` leaves success confirmation to the world. The files do **not** use `@explicitHints`, which makes hints show by default, or `@unifiedToolbox`, which flattens the toolbox (the two faults reported on the first bell tutorial). They do not use `@flyoutOnly` either.
- Hints sit under `#### ~ tutorialhint`, so they appear only when asked for. Every step has a `blocks` or `ghost` fence, so its toolbox stays filtered.
- Each Notebook page stays under about 600 characters (the specification's QA-01).
- Fences are MakeCode Static TypeScript for the Minecraft target (`player.onChat`, `agent.teleport`, `agent.move`, `agent.turn`, `agent.inspectBlock`, `loops.pause`, `player.say`). The older `agent.inspect(AgentInspection.Block, …)` is deprecated in the current target and is not used.

## Publishing and the cache

Merging to the default branch publishes. MakeCode caches GitHub tutorials, so **bump `version` in `pxt.json` on every content change**; otherwise a good push looks like a failed deploy. Every tutorial file must be listed in `pxt.json` `files`, or MakeCode returns a 404 for it.

## Welsh

`_locales/cy/` is empty on purpose. A Welsh mirror (`_locales/cy/<same-name>.md`, registered in `pxt.json`) is added only from Welsh supplied by Sarah (Cadw), never from placeholders or machine translation.

## Open items

These are tracked on the Raglan card (Cadw Galeri 3). The tutorials follow Sarah's text where her sources are open, and nothing here is filled in by guesswork.

**Waiting on Sarah**
1. **Q2C starter (plan question 5).** Her screenshot shows two presses of Bell 1, ending on the plate, with a loose `turn left` block and a loose `repeat 3` block. Her text says the starter sends S and returns the Agent to the start. The draft follows her text. Loose blocks cannot be put in a template, so those two are offered in the toolbox instead. What Bell 3 is for is also still open; it is kept but not scored.
2. **Q2E loop counts and counts checking (plan question 6).** Her `repeat 9` (and the `repeat 5` row pairs in her final code) fit a 10 × 10 interior. Galeri 3's garden has 12 × 12 clear cells, which needs 11 moves per row and 6 pairs. Her numbers are kept, and the route hint tells the learner to count the moves to the far fence. The world only checks coverage, not the counts.
3. **Q2E page order.** Test page 1 sits after Modify page 2, in the order of her Learner Task. Her stage table lists Modify pages 1–3 before Test pages 1–2.
4. **Welsh (plan question 1)** for both tutorials.

**Check in client (first Code Builder test)**
- `agent inspect block forward = Wildflowers` (and `= Leaf Litter`) is true in front of the garden's targets. The names `WILDFLOWERS`, `LEAF_LITTER` and `ROSE_BUSH` exist in the current MakeCode Minecraft target (checked 30 Sep 2026).
- Hints appear only on request, the toolbox shows filtered categories, and Next/Back reaches every page. Check the last page has no Done button.
- The text `join` block is under ADVANCED then TEXT, as Sarah's text says.
- The garden has no Rose Bushes yet, so the optional Boolean OR extension cannot be tried in the world.
