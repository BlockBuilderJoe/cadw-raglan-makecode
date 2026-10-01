### @hideDone true

# Edward's Mechanical Gardener

```template
player.onChat("check", function () {
    agent.teleport(world(8521, -1, 16945), NORTH)
    for (let index = 0; index < 9; index++) {
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
    agent.move(FORWARD, 1)
    agent.turn(RIGHT_TURN)
})
```

## Plan @showdialog

**“Every successful invention begins with a plan.”**

I designed my Mechanical Gardener to tend the whole garden – but an invention is no use if it misses half the work! If you were guiding my Gardener, what route would you choose?

Before you investigate my program:

* discuss the route with your partner;
* put the movements and turns in the order they need to happen;
* record your plan using pseudocode or a flow diagram;
* look carefully for any movements that repeat.

Keep your plan close. Soon we shall see whether my program behaves as you expect!

```ghost
agent.move(FORWARD, 1)
agent.turn(RIGHT_TURN)
for (let index = 0; index < 9; index++) {
}
```

## Predict

**“An inventor should never set a machine in motion without first considering what it might do!”**

I have left you part of my Mechanical Gardener program. Study it carefully before you run it.

What do you predict will happen? Where will the Agent move? Which way will it turn? Where do you think it will stop? Will it tend the whole garden?

Make your prediction before you put my invention to the test.

```ghost
agent.move(FORWARD, 1)
agent.turn(RIGHT_TURN)
for (let index = 0; index < 9; index++) {
}
```

## Run

**“A plan may look excellent on paper, but an inventor must put it to the test!”**

Run my program using the check command and watch the Mechanical Gardener carefully. For now, resist the temptation to change anything. Let the program finish and watch exactly what the Agent does.

Was your prediction correct?

Press the green Play button, then type **check** in the Minecraft chat.

```ghost
agent.move(FORWARD, 1)
agent.turn(RIGHT_TURN)
for (let index = 0; index < 9; index++) {
}
```

## Observe

**“Interesting! Now we have some evidence.”**

Compare what my Mechanical Gardener actually did with what you predicted. Look carefully at the garden:

* Which parts did the Agent cover?
* Where did it stop?
* Which parts of the garden are still untouched?
* What movements would it need to make next?

Do not change my program just yet. First decide what you think is missing.

```ghost
agent.move(FORWARD, 1)
agent.turn(RIGHT_TURN)
for (let index = 0; index < 9; index++) {
}
```

## Debug

**“Even the finest inventions rarely work perfectly the first time.”**

My Mechanical Gardener has followed its instructions – but those instructions are not yet enough to tend the whole garden. Can you work out what needs to change?

Use your plan and your observations as evidence. Look for:

* movements that are missing;
* turns that need to be added;
* a pattern that could be repeated.

Find the problem before you try to fix it. That is how an inventor improves a machine.

```ghost
agent.move(FORWARD, 1)
agent.turn(RIGHT_TURN)
for (let index = 0; index < 9; index++) {
}
```

#### ~ tutorialhint

**Notebook Observation 1 – Movement & Loops**

“A curious pattern has appeared in my notes…”

Watch the Gardener’s route carefully. Once it has travelled across one row and returned along the next, what happens to the pattern?

Ask yourself: Which movements happen again? Which turns happen again? Could one set of instructions be repeated instead of written several times?

An inventor who spots a pattern can often find a simpler solution.

## Modify – page 1

**“Now we can improve my invention!”**

First, my Mechanical Gardener needs to reach the whole garden. Use the pattern you discovered to complete its route.

Look at the movements carefully. Are you giving the Agent the same instructions again and again? If a pattern repeats, could a loop do the repeating for you?

Make your changes, then get ready to test whether my Gardener can finally cover the whole garden.

```ghost
agent.move(FORWARD, 1)
agent.turn(RIGHT_TURN)
for (let index = 0; index < 9; index++) {
}
```

#### ~ tutorialhint

Example intermediate movement logic showing the Agent completing two garden rows. Further logic is still required to repeat this movement pattern across the whole garden.

Count the moves the Agent needs to reach the far fence, and the pairs of garden rows, before you set each repeat number.

```blocks
player.onChat("check", function () {
    agent.teleport(world(8521, -1, 16945), NORTH)
    for (let index = 0; index < 9; index++) {
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
    agent.move(FORWARD, 1)
    agent.turn(RIGHT_TURN)
    for (let index = 0; index < 9; index++) {
        agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})
```

## Modify – page 2

**“Excellent! My Gardener can travel – but a true gardener must notice what is growing around it.”**

At the moment, the Agent moves without knowing what it finds. Can you give my Mechanical Gardener the power to make a decision?

Use an if condition with the Agent’s inspection so that your Mechanical Gardener can make a decision when it detects:

* a Wildflower;
* Leaf Litter.

Think carefully about the condition. What must be true before the Agent carries out each action?

```ghost
agent.move(FORWARD, 1)
agent.turn(RIGHT_TURN)
for (let index = 0; index < 9; index++) {
}
if (agent.inspectBlock(FORWARD) == WILDFLOWERS) {
    player.say("Wildflower")
}
```

#### ~ tutorialhint

**Notebook Observation 2 – Conditionals**

“Moving around the garden is only half the problem.”

My Gardener needs to decide what it has found before it knows what to do next. Think about an if condition: IF the Agent detects a Wildflower, what should happen? IF it detects Leaf Litter, what should happen instead?

Look carefully at what the Agent is inspecting and make sure each condition is checking for the correct block. A machine can only make the right decision if we give it the right condition.

## Test – page 1

**“Every improvement must earn its place by surviving a test.”**

Run your Mechanical Gardener and watch closely. Does it:

* follow the route you planned?
* cover the whole garden?
* recognise Wildflowers correctly?
* recognise Leaf Litter correctly?

If something does not behave as you expected, use what you observe to find the problem. Make one careful change and test again.

Press Play and type **check**; the world checks the Agent's route through the garden.

```ghost
agent.move(FORWARD, 1)
agent.turn(RIGHT_TURN)
for (let index = 0; index < 9; index++) {
}
if (agent.inspectBlock(FORWARD) == WILDFLOWERS) {
    player.say("Wildflower")
}
```

#### ~ tutorialhint

In BLOCKS, change the grass block to the wildflower block. The if block should look like this:

```blocks
if (agent.inspectBlock(FORWARD) == WILDFLOWERS) {
    player.say("Wildflower")
}
```

Put the if statement into the main code. An if statement for detecting the leaf litter now needs to be created and put into the main code.

## Modify – page 3

**“Our Gardener can move and make decisions. But can it remember what it has found?”**

Recognising a Wildflower or Leaf Litter is useful – but I want to know how many it discovers. Create variables to keep track of:

* Wildflowers;
* Leaf Litter.

Begin each count at 0. Each time the Agent detects a Wildflower or Leaf Litter, increase the correct variable by 1.

Now my Mechanical Gardener can do more than react – it can keep a record of what it finds!

```ghost
agent.move(FORWARD, 1)
agent.turn(RIGHT_TURN)
for (let index = 0; index < 9; index++) {
}
if (agent.inspectBlock(FORWARD) == WILDFLOWERS) {
    player.say("Wildflower")
}
let wildFlower = 0
wildFlower += 1
```

#### ~ tutorialhint

**Notebook Observation 3 – Variables**

“I know my Gardener can recognise what it finds – but how shall we remember how many it has seen?”

Imagine keeping two tally marks in my notebook: one for Wildflowers and one for Leaf Litter. A variable can do the same job inside your program.

Think about: what each variable needs to remember; what number each variable should begin with; when the correct variable should increase by 1.

Make sure the Gardener updates the right count each time it discovers something.

## Modify – show the counts

To say how many of each plant you have, you need to go to ADVANCED then TEXT. Change “Hello” to “Wildflowers:” and add your wildFlower variable to “World” and add to a SAY block.

Do the same with “LeafLitter:” and your leafLitter variable, each inside its own if statement.

```ghost
agent.move(FORWARD, 1)
agent.turn(RIGHT_TURN)
for (let index = 0; index < 9; index++) {
}
if (agent.inspectBlock(FORWARD) == WILDFLOWERS) {
    player.say("Wildflower")
}
let wildFlower = 0
wildFlower += 1
player.say("Wildflowers:" + wildFlower)
```

#### ~ tutorialhint

Go to VARIABLES and Make a Variable called wildFlower, then another called leafLitter. Set your variables at the start of your code, and remember to add the change leafLitter by 1 to your if statements.

```blocks
let leafLitter = 0
let wildFlower = 0
if (agent.inspectBlock(FORWARD) == WILDFLOWERS) {
    wildFlower += 1
    player.say("Wildflowers:" + wildFlower)
}
```

## Test – page 2

**“One final experiment. Let us see whether all the parts of my invention work together!”**

Run the complete program from the beginning. Watch the Gardener and check its results. Does it:

* travel through the whole garden?
* identify Wildflowers and Leaf Litter correctly?
* increase the correct variable each time?
* give you the correct totals at the end?

If the results are not right, investigate why, improve the program and test it again. An invention is not finished simply because it runs – it must do its job correctly.

```ghost
agent.move(FORWARD, 1)
agent.turn(RIGHT_TURN)
for (let index = 0; index < 9; index++) {
}
if (agent.inspectBlock(FORWARD) == WILDFLOWERS) {
    player.say("Wildflower")
}
let wildFlower = 0
wildFlower += 1
player.say("Wildflowers:" + wildFlower)
```

## Reflect

**“Splendid! My Mechanical Gardener has become quite a capable invention.”**

Think back to the program you started with. Can you explain:

* how the algorithm controls its route?
* how a loop helps with repeated movement?
* how conditions allow it to make decisions?
* how variables help it remember what it finds?

Which part did you have to test or improve most carefully?

Remember: an inventor does not simply make something work – an inventor understands why it works.

When the world has confirmed your Mechanical Gardener, speak to Owain.

```ghost
agent.move(FORWARD, 1)
agent.turn(RIGHT_TURN)
for (let index = 0; index < 9; index++) {
}
if (agent.inspectBlock(FORWARD) == WILDFLOWERS) {
    player.say("Wildflower")
}
let wildFlower = 0
wildFlower += 1
player.say("Wildflowers:" + wildFlower)
```

## Optional extension – Boolean OR

**“I have been wondering whether my Gardener might recognise more than one kind of flower…”**

Suppose the garden contains both Wildflowers and Rose Bushes. I would like my Gardener to count either of them as a Flower. Do we really need two completely separate decisions?

Explore the Logic blocks and look for or. Can you create a condition that is true when the Agent detects a Wildflower OR a Rose Bush?

Then consider what variable you could use to keep one total for all the Flowers it finds.

Now that would make my Mechanical Gardener a little more sophisticated!

```ghost
agent.move(FORWARD, 1)
agent.turn(RIGHT_TURN)
for (let index = 0; index < 9; index++) {
}
if (agent.inspectBlock(FORWARD) == WILDFLOWERS) {
    player.say("Wildflower")
}
if (false || false) {
}
let flowers = 0
flowers += 1
player.say("Flowers:" + flowers)
```

#### ~ tutorialhint

Go to LOGIC for or. Use your inspect block from before, and create a new inspect block for a rose bush. Create a variable called flowers.

```blocks
let flowers = 0
if (agent.inspectBlock(FORWARD) == WILDFLOWERS || agent.inspectBlock(FORWARD) == ROSE_BUSH) {
    flowers += 1
    player.say("Flowers:" + flowers)
}
```
