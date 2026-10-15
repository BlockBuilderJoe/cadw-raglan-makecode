# Cadw Raglan Castle — Code Builder tutorials

Guided Minecraft Education Code Builder (MakeCode) tutorials for the Raglan Castle journey on Cadw Galeri 3. All three run in the Blocks editor. The learning design, starter programs, Edward's Workshop Notebook pages and Notebook Observations come from Cadw's activity specifications (Q2C v3.2, Q2E v2.3, Q3D v2.5). The Notebook pages are the steps, and the Observations are the hints.

## The activities

| File | Activity | Opened from | Chat command | Starter | The learner adds |
| --- | --- | --- | --- | --- | --- |
| `q2c-bells.md` | Q2C Edward's Bell Communication System | Technocamps Mentor, **Start Coding**, in the cellar workshop | `ring` | Teleports the Agent and sends the first S: three rings of Bell 1, returning to the start | Turn towards Bell 2, send O, return to Bell 1, send the final S. Optional: loops and a function |
| `q3d-water-engine.md` | Q3D Edward's Water Commanding Engine | Techno Mentor, **Start Coding**, at the Water Commanding Engine Modelling Area (the learner bay) | `run` | Teleports the Agent to its gold pad (8708 11 16950, facing south) and sets grass ×64 in slot 1 (Sarah's DD-03: the teleport and initial set item) | The sequence that operates their own model: test for their gate block in the channel; if it is there, interact with the lever (on the Agent's right in the prototype); drop one item forward in both cases; pauses as needed |
| `q2e-gardener.md` | Q2E Edward's Mechanical Gardener | Technocamps Mentor, **Start Coding**, in the Terraced Gardens | `check` | Teleports the Agent, crosses one row (`repeat 9`) and turns into the next | A full lawnmower route with loops; `if` and Agent inspection for Wildflowers and Leaf Litter; the variables `wildFlower` and `leafLitter` (start at 0, change by 1); `say` for each count. Optional: Boolean OR with Rose Bushes |

## Open in Code Builder

The Mentor's **Start Coding** button runs `codebuilder navigate @s true <url>` with these exact URLs:

- Q2C: https://minecraft.makecode.com/?ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:github:BlockBuilderJoe/cadw-raglan-makecode/q2c-bells
- Q2E: https://minecraft.makecode.com/?ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:github:BlockBuilderJoe/cadw-raglan-makecode/q2e-gardener
- Q3D: https://minecraft.makecode.com/?ingame=1&ipc=1&noRunOnX=1&lockedEditor=1#tutorial:github:BlockBuilderJoe/cadw-raglan-makecode/q3d-water-engine

Q3D's and Q3E's "reopen your existing program" buttons (Debug My Code, Start Testing, Refine My Code, Start Retest) open Code Builder without a tutorial (`https://minecraft.makecode.com/?ingame=1&ipc=1&noRunOnX=1`), where the learner's own project is in My Projects: a tutorial URL starts again from its template.

When testing, add `skipgithubcache=1` after `?`. Never add a second `#branch` fragment: the default branch is what learners get.

## The world confirms success

The learner presses the green Play button, which registers the chat command, and then types `ring` or `check` in the Minecraft chat. The Raglan runtime on Galeri 3 watches the Agent, not the code. The tutorials never announce success themselves (`@hideDone`), and they never ask the learner to add code that reports its own success.

- **Q2C.** The Agent starts at 8623 7 16941, facing north. Bell 1's plate is one block ahead (Z16940) and Bell 2's is one block behind (Z16942). Bell 3 (Z16944) is not part of the S–O–S. A ring counts only when the Agent, not the player, presses the plate. The world passes Bell 1 ×3, Bell 2 ×3, Bell 1 ×3 and says "The bells sent S-O-S. Speak to Owain." A wrong run names the first ring that differs.
- **Q2E.** The Agent starts at 8521 -1 16945, facing north (−Z), in the bottom-left corner of a 12 × 12 oak fence round 10 × 10 clear cells (X8521–8530, Z16936–16945; Galeri 3 1.0.957, 14 Oct 2026), so Sarah's `repeat 9` reaches the far fence and five two-row passes cover it. The world passes a route that covers every cell and never leaves the garden, then names the Wildflowers and Leaf Litter the Agent reached. It cannot read `say`, so the counts are for the learner to check.

- **Q3D.** The learner builds their own model in the bay: a channel from where the Agent drops the item to the lift's inlet (8711 10 16963), a sticky piston that pushes their gate block into the channel when their lever is on, and the lever. The lift column and catcher are fixed. The world passes It Worked only when an item the learner's own Agent dropped reaches the catcher. The tutorial's example test position (8708 10 16953, three blocks in front of the pad at channel level) and gate block (Sandstone: sand is refused in the court because it falls) are only examples; learners adjust them to their own model.

## Format rules

- Metadata is `### @hideDone true` and `### @explicitHints true`. Keep step controls visible: `@hideIteration true` hides Previous/Next and the step counter, trapping these multi-step lessons at Predict. `lockedEditor=1` keeps the learner in the tutorial and `@hideDone` leaves success confirmation to the world. `@explicitHints true` makes the tutorial parser split each authored `#### ~ tutorialhint` from its caption. Without it, prose-only hints render in the caption as raw headings: hidden `ghost` fences do not create a hint boundary. Keep the categorized toolbox; do not enable `@unifiedToolbox` or `@flyoutOnly`. Hint visibility must be checked in the Minecraft client.
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
2. **Q2E counts checking (plan question 6).** Resolved for the loop counts: the garden was rebuilt to Sarah's 12 × 12 fence round 10 × 10 cells (14 Oct 2026), so her `repeat 9` and `repeat 5` fit. The world checks coverage and names the plants reached; it cannot read the learner's counts.
3. **Q2E page order.** Test page 1 sits after Modify page 2, in the order of her Learner Task. Her stage table lists Modify pages 1–3 before Test pages 1–2.
4. **Welsh (plan question 1)** for both tutorials.

5. **Q3D toolbox (Sarah's images 2-6).** Her final solution uses `pause (ms) 1000`, which is not among the toolbox images; it is offered in the toolbox. Her Complete page says "He'll"; the Techno Mentor is female, so the tutorial says "She'll".

**Check in client (first Code Builder test)**
- Q3D: the template teleports the Agent onto its pad facing south and gives it grass in slot 1; `test for block` at a world position, `agent interact right` and `agent drop forward from slot 1 amount 1` all work on Galeri 3. Reopening Code Builder from the Mentor's Debug My Code shows the learner's project in My Projects.
- `agent inspect block forward = Wildflowers` (and `= Leaf Litter`) is true in front of the garden's targets. The names `WILDFLOWERS`, `LEAF_LITTER` and `ROSE_BUSH` exist in the current MakeCode Minecraft target (checked 30 Sep 2026).
- Hints appear only on request, the toolbox shows filtered categories, and Next/Back reaches every page. Check the last page has no Done button.
- The text `join` block is under ADVANCED then TEXT, as Sarah's text says.
- The garden has no Rose Bushes yet, so the optional Boolean OR extension cannot be tried in the world.
