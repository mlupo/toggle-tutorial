# It's Toggle Time!

## It's Toggle Time! @unplugged
In this tutorial we will toggle a bunch of LEDs on the screen, and automate it useing the power of functions!

![A toggling micro:bit!](https://raw.githubusercontent.com/mlupo/toggle-tutorial/master/docs/static/toggle2.gif)

## _
### Start with a button
First, open the ``||input:input||`` drawer, and drag the ``||input:on button A pressed||`` block into the workspace.  

```blocks
input.onButtonPressed(Button.A, function () {
	
})
```

## _
### Toggle a Single LED
Open the ``||led:Led||`` drawer, and find the ``||led:toggle x 0 y 0||`` block.  
Snap that block into the ``||input:on button A pressed||`` block in the workspace.  

Press the A button a few times to check your code so far.

```blocks
input.onButtonPressed(Button.A, function on_button_pressed_a() {
    led.toggle(0, 0)
})
```

## _ @fullscreen
### Let's Make it Random!
Next, we will add a bit of randomness to our toggling!  
The Led columns are numbered 0 to 4, from left to right, and the rows are numbered 0 to 4 from the top down. With these numbers we can make random leds appear all over the screen.  

From the ``||math:math||`` drawer, and pull out the ``||math:pick random 0 to 10||`` block.
Put this block into the **0** beside the letter **x** in the toggle block. In the random block, change the number 10 to the number 4.

```blocks
input.onButtonPressed(Button.A, function () {
    led.toggle(randint(0, 4), 0)
})
```

## _ 
### Let's Make it Random-er!
Repeat the last step to put the same ``||math:pick random 0 to 4||`` block into the **0** beside the letter **y** in the toggle block.  

Again, press the A button a few times to test out your code!

```blocks
input.onButtonPressed(Button.A, function () {
    led.toggle(randint(0, 4), randint(0, 4))
})
```

## _ @unplugged
### Hold on! We're going to introduce something new!
If you made it to this part, let the instructor know! We are going to introduce some new things before moving on.

Here is a sneak peek:

```blocks
function superToggle (num: number, sleep: number) {
    for (let index = 0; index < num; index++) {
        led.toggle(randint(0, 4), randint(0, 4))
        basic.pause(sleep)
    }
}
```