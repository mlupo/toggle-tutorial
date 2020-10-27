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

Press the A button on the micro:bit in the simulator a few times to check your code so far.

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
Put this block into the **0** beside the letter **x** in the toggle block. In the ``||math:random||`` block, change the number 10 to the number 4.

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

## _ 
### Let's get functional!
We are taking  a big leap, and we're going to learn about functions!  
Start by clicking the **Advanced** label to expose the ``||functions:functions||`` drawer. Open the ``||functions:functions||`` drawer and click **Make a Function**.

In the window that appears, give  your function a good name, and click the **number** button twice. This gives the function 2 arguments that we can fill in later.
Rename **num2** to **sleep**.

![Editing functions](https://raw.githubusercontent.com/mlupo/toggle-tutorial/master/docs/static/edit_function.png)

## _ 
### Let's add a loop
As a result of your last step, your function should have appeared in the workspace.  
Open the ``||loops:loops||`` drawer, find the ``||loops:repeat 4 times||`` block, and place it inside your function.  
Drag the **num** bubble from the function, and place it over the number 4 in the ``||loops:repeat||`` block.  

![using arguments](https://raw.githubusercontent.com/mlupo/toggle-tutorial/master/docs/static/use_argument.gif)

```blocks
function superToggle (num: number, sleep: number) {
    // @highlight
    for (let index = 0; index < num; index++) {
    	
    }
}
```

## _
### Move that toggle block
Next, click and drag the ``||led:toggle||`` block you created in the ``||input:on button A pressed||``, and move it indside the ``||loops:loop||`` within your ``||functions:function||``.  

This will make it so that when we run our function, our toggle code will be repeated.

```blocks
function superToggle (num: number, sleep: number) {
    for (let index = 0; index < num; index++) {
        // @highlight
        led.toggle(randint(0, 4), randint(0, 4))
    }
}
```

## _
### Add a pause
One of the last steps we need to do is add a pause into our loop.  
Open the ``||basic:basic||`` drawer, find the ``||basic:pause (ms) 100||``, and place it **underneath** the ``||led:toggle||`` block in our function.  

Click and drag the ``||variables:sleep||`` bubble from the function, and place it over the number **100** in the ``||basic:pause||`` block.

```blocks
function superToggle (num: number, sleep: number) {
    for (let index = 0; index < num; index++) {
        led.toggle(randint(0, 4), randint(0, 4))
        // @highlight
        basic.pause(sleep)
    }
}
```

## _
### Now let's use this function!
To use a function, it needs to be **called**. Back in the functions drawer, there is new ``||functions:call||`` block which includes the name of your new function.   Drag a ``||functions:call||`` block into the ``||input:on button A pressed||`` block leftover from earlier.  

The ``||functions:call||`` block will run your function with the parameters you specify. Based on our function's code, the first number is the number of times the loop will run, and the second number is how long to wait inbetween loops.  
Enter the numbers **100** and **50**, then press the A button in the micro:bit simulator to see what happens!

```blocks
// @highlight
input.onButtonPressed(Button.A, function () {
    superToggle(100, 50)
})

function superToggle (num: number, sleep: number) {
    for (let index = 0; index < num; index++) {
        led.toggle(randint(0, 4), randint(0, 4))
        basic.pause(sleep)
    }
}
```

## _ @unplugged
### WHOA! You did it!!
You learned how to use a function! That's amazing!!! Even if it still seems really confusing, don't worry! Let the instrutor know that you're done, and we will start on the next project.

## _ @unplugged
### Press the Finish Button
To end this tutorial