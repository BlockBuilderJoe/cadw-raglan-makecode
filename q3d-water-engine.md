### @explicitHints true
### @hideDone true

# Edward's Water Commanding Engine

```template
player.onChat("run", function () {
    agent.teleport(world(8708, 11, 16950), SOUTH)
    agent.setItem(GRASS, 64, 1)
})
```

## Plan @showdialog

**“Every successful invention begins with a plan.”**

My Water Commanding Engine needs the Agent to carry out a series of actions in the correct order. What will your Agent need to do?

Before you begin programming:

* discuss the actions with your partner;
* put them in the order they need to happen;
* record your plan using pseudocode or a flow diagram.

When you are happy with your plan, you are ready to begin.

```ghost
agent.interact(RIGHT)
agent.drop(FORWARD, 1, 1)
if (blocks.testForBlock(SANDSTONE, world(8708, 10, 16953))) {
}
loops.pause(1000)
```

## Predict

**“A good inventor thinks ahead before putting a plan to the test.”**

Look again at the algorithm you have created. What do you predict your Agent will do when these instructions become a program?

Talk through your prediction with your partner. Explain what you expect the Agent to do, step by step.

Keep your prediction in mind – soon you will find out if your Agent behaves as you expect.

```ghost
agent.interact(RIGHT)
agent.drop(FORWARD, 1, 1)
if (blocks.testForBlock(SANDSTONE, world(8708, 10, 16953))) {
}
loops.pause(1000)
```

## Run

**“Now it is time to put your plan into action.”**

Use your algorithm to complete the program for your Agent. My starter sends the Agent to its gold pad, facing south, and gives it grass to drop. If your model is laid out differently, change the Agent's coordinates and direction to suit it.

Check that the Agent has the information it needs to operate the Water Commanding Engine. Press the green Play button, type **run** in the Minecraft chat and watch your Agent carefully. Does it behave as you predicted?

```ghost
agent.interact(RIGHT)
agent.drop(FORWARD, 1, 1)
if (blocks.testForBlock(SANDSTONE, world(8708, 10, 16953))) {
}
loops.pause(1000)
agent.move(FORWARD, 1)
agent.turn(LEFT_TURN)
```

## Observe

**“An inventor must watch carefully – even when things do not go to plan.”**

Watch your Agent as it tries to operate your Water Commanding Engine. What happened? Did the Agent carry out the actions in the order you expected?

Compare what you observed with your prediction. Notice where the Agent's behaviour matched your plan – and where it did not.

```ghost
agent.interact(RIGHT)
agent.drop(FORWARD, 1, 1)
if (blocks.testForBlock(SANDSTONE, world(8708, 10, 16953))) {
}
loops.pause(1000)
```

#### ~ tutorialhint

**Notebook Observation 1**

“Look carefully before changing anything. Compare your plan with what your Agent actually did. Where did its behaviour first differ from what you expected?”

## Debug

**“Not quite what you expected? That is all part of inventing!”**

Look closely at the part of your program where the Agent's behaviour differed from your plan. Which instruction – or missing instruction – could be causing the problem?

Compare your program with your algorithm and trace the instructions step by step. Can you identify what needs to change before you try again?

```ghost
agent.interact(RIGHT)
agent.drop(FORWARD, 1, 1)
if (blocks.testForBlock(SANDSTONE, world(8708, 10, 16953))) {
}
loops.pause(1000)
```

#### ~ tutorialhint

**Notebook Observation 2**

“Follow your Agent's actions one step at a time. At what point does what it does begin to differ from your plan?”

## Modify

**“A small change can make a big difference.”**

You have identified where your program may need improving. What change could you make to help your Agent behave as you intended?

Update your algorithm if needed, then make the corresponding change to your program. Be ready to test whether your change has improved your solution.

```ghost
agent.interact(RIGHT)
agent.drop(FORWARD, 1, 1)
if (blocks.testForBlock(SANDSTONE, world(8708, 10, 16953))) {
}
loops.pause(1000)
```

#### ~ tutorialhint

**Notebook Observation 3**

“You have found where things begin to go wrong. Now look closely at the instructions at that point. What does your Agent need to know before it decides what to do next?”

## Test

**“Every change needs to be put to the test.”**

Run your revised program and watch your Agent carefully. Does it now carry out the sequence of actions you intended? Does your Water Commanding Engine operate successfully?

If something still does not work as expected, use what you observe to decide what needs further investigation.

```ghost
agent.interact(RIGHT)
agent.drop(FORWARD, 1, 1)
if (blocks.testForBlock(SANDSTONE, world(8708, 10, 16953))) {
}
loops.pause(1000)
```

#### ~ tutorialhint

**Notebook Observation 4**

“Sometimes an invention needs to make a decision.”

Think about the point you have identified. Is there something your Agent needs to check before it carries out its next action?

Look at the blocks available in your toolbox. Which one could help your program make that decision?

## Reflect

**“A successful invention is more than a working machine – it is what we learn from making it work.”**

Think back to the algorithm you planned at the beginning. How did your plan become instructions for your Agent? What did testing your program help you discover? How did the changes you made improve your solution?

Talk about what you would do differently if you programmed your Water Commanding Engine again.

```ghost
agent.interact(RIGHT)
agent.drop(FORWARD, 1, 1)
if (blocks.testForBlock(SANDSTONE, world(8708, 10, 16953))) {
}
loops.pause(1000)
```

## Complete

Your program is ready. Now it's time to test it with your Water Commanding Engine.

Return to the Techno Mentor in the Water Commanding Engine Modelling Area. She'll help you test whether the Agent can follow your instructions and operate your model as you planned.

```ghost
agent.interact(RIGHT)
agent.drop(FORWARD, 1, 1)
```
