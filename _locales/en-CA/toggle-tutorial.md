# It's Toggle Time!

## It's Toggle Time! @unplugged
In this tutorial we will toggle a bunch of LEDs on the screen, and automate it useing the power of functions!

![A toggling micro:bit!](https://raw.githubusercontent.com/mlupo/toggle-tutorial/master/docs/static/toggle.GIF)

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

The two zeros can be changed, and you can experriment with how different values change which Leds light up.

```blocks
input.onButtonPressed(Button.A, function on_button_pressed_a() {
    led.toggle(0, 0)
})
```