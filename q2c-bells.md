### @explicitHints true
### @hideDone true

# Edward's Bell Communication System

```template
player.onChat("ring", function () {
    agent.teleport(world(8623, 7, 16941), NORTH)
    loops.pause(1000)
    agent.move(FORWARD, 1)
    loops.pause(1000)
    agent.move(BACK, 1)
    loops.pause(1000)
    agent.move(FORWARD, 1)
    loops.pause(1000)
    agent.move(BACK, 1)
    loops.pause(1000)
    agent.move(FORWARD, 1)
    loops.pause(1000)
    agent.move(BACK, 1)
    loops.pause(1000)
})
```

## Plan @showdialog

**"Every invention begins with a plan."**

Before I tested any new idea, I carefully thought about how every part should work together. Study my Bell Communication System. How do you think the Agent should move between the bells to transmit the SOS message?

Before opening the program:

* Discuss your ideas with your partner.
* Sketch a simple flow diagram or write pseudocode if it helps.

When you are ready, open my starter program and begin your investigation.

```ghost
agent.move(FORWARD, 1)
agent.move(BACK, 1)
agent.turn(LEFT_TURN)
loops.pause(1000)
for (let index = 0; index < 3; index++) {
}
```

## Predict

**"Never trust a machine until you have tested it."**

Every inventor has an idea about what a machine should do before they test it. Study my starter program carefully.

What do you think will happen when it runs? Will the Agent successfully transmit the complete SOS message? Or is something missing?

Make your prediction before you test your theory.

```ghost
agent.move(FORWARD, 1)
agent.move(BACK, 1)
agent.turn(LEFT_TURN)
loops.pause(1000)
for (let index = 0; index < 3; index++) {
}
```

## Run

**"An inventor learns by testing ideas, not by guessing."**

You have studied the Bell Communication System and made your prediction. Now it is time to test your theory. Run my starter program and watch the Agent carefully.

Did the machine behave exactly as you expected? Pay close attention to every movement—you may discover an important clue.

Press the green Play button, then type **ring** in the Minecraft chat.

```ghost
agent.move(FORWARD, 1)
agent.move(BACK, 1)
agent.turn(LEFT_TURN)
loops.pause(1000)
for (let index = 0; index < 3; index++) {
}
```

## Observe

**"Even the finest inventions reveal their secrets to those who observe carefully."**

Was your prediction correct? Where did the communication stop?

Which part of the SOS message was successfully transmitted...

...and which part was missing?

Before changing anything, decide what you think has gone wrong.

```ghost
agent.move(FORWARD, 1)
agent.move(BACK, 1)
agent.turn(LEFT_TURN)
loops.pause(1000)
for (let index = 0; index < 3; index++) {
}
```

#### ~ tutorialhint

**Notebook Observation 1**

"Look carefully before changing anything. Which part of the SOS message was completed successfully?"

## Debug

**"Mistakes are not failures—they are clues waiting to be understood."**

Every inventor discovers that even the best ideas need refining. Study the program carefully. Which instruction is missing? Which part of the communication sequence needs to change?

Make one thoughtful improvement at a time, then test your thinking.

Remember... understanding why something failed is often more valuable than fixing it quickly.

```ghost
agent.move(FORWARD, 1)
agent.move(BACK, 1)
agent.turn(LEFT_TURN)
loops.pause(1000)
for (let index = 0; index < 3; index++) {
}
```

#### ~ tutorialhint

**Notebook Observation 2**

"Compare what you expected with what actually happened. Which instruction do you think is missing?"

## Modify

**"A good inventor is never satisfied with the first solution."**

Repairing a problem is only the beginning. Continue my work by extending my program so the Agent completes the full SOS communication sequence.

As you work, think carefully about every instruction you add. A well-designed solution is not simply one that works—it is one that works clearly, logically and with purpose.

Add your blocks to the end of ``||player:on chat command||`` so the Agent turns towards Bell 2, transmits O, returns to Bell 1 and completes the final S.

```ghost
agent.move(FORWARD, 1)
agent.move(BACK, 1)
agent.turn(LEFT_TURN)
loops.pause(1000)
for (let index = 0; index < 3; index++) {
}
```

#### ~ tutorialhint

**Notebook Observation 3**

"Change just one part of my program before testing it again. Every careful improvement teaches us something."

## Test

**“A machine is not proven by working once.”**

You have repaired and extended my program. Now test the complete Bell Communication System from beginning to end. Watch every movement carefully.

Does the Agent transmit S–O–S in the correct order? Do the bells ring the correct number of times?

If the result is not quite right, return to your program and make one careful change before testing again. A dependable invention should work correctly every time.

Press Play and type **ring**: the world checks the bells and tells you when to speak to Owain.

```ghost
agent.move(FORWARD, 1)
agent.move(BACK, 1)
agent.turn(LEFT_TURN)
loops.pause(1000)
for (let index = 0; index < 3; index++) {
}
```

## Reflect

**"Every invention teaches us something, whether it succeeds or fails."**

Take a moment to look back at your investigation. You began with a plan. You made a prediction. You tested your ideas. You discovered a problem. You improved the solution.

What did you learn that you didn't know when you first opened my notebook?

Remember... every successful inventor carries today's discoveries into the next investigation.

When the world has confirmed your S–O–S, speak to Owain.

```ghost
agent.move(FORWARD, 1)
agent.move(BACK, 1)
agent.turn(LEFT_TURN)
loops.pause(1000)
for (let index = 0; index < 3; index++) {
}
```

## Optional extension

This page is optional, once the world has confirmed your S–O–S.

**Notebook Observation 4 (Optional Extension)**

"Your invention now works... but can it work more elegantly? Could repeated instructions be simplified?"

```ghost
agent.move(FORWARD, 1)
agent.move(BACK, 1)
agent.turn(LEFT_TURN)
loops.pause(1000)
for (let index = 0; index < 3; index++) {
}
function sendLetter () {
}
sendLetter()
```

#### ~ tutorialhint

Look for repeated patterns in your program. Repeated instructions can be simplified using a Repeat Loop, and a Function can represent the repeated behaviour required to transmit a letter.

```blocks
for (let index = 0; index < 3; index++) {
    agent.move(FORWARD, 1)
    loops.pause(1000)
    agent.move(BACK, 1)
    loops.pause(1000)
}
```
