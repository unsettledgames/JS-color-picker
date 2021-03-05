# JS-colour-picker
Colour picker with extra features written in JavaScript.

![JS colour picker](showcase.gif)

## Requirements:
- Node

## How to install and run
- Run `npm-install` from the JS-colour-picker folder
- Run `npm run test` to run the project

## Features
- Three different colour picking modes (RGB, HSV and HSL)
- Six different colour harmonies (mono, analogous, complementary, split complementary, triadic, tetradic)
- Sliders that update depending on the current input, always showing the colour the user would get if they moved the slider
- Possibility to insert numerical values instead of using the sliders
- Colour and hex value previews
- Mini colour picker for more intuitive colour picking

## How it works
There are three ways to edit the current colour:
- Sliders
- Textboxes
- The minipicker
Every time one of these components is updated, the changes are reflected on all the other ones:
- `inputChanged` is triggered when the value of a textbox changes: it updates the corresponding slider, which also update the minipicker
- `updateSliderValue` is triggered the value of a slider changes: it updates the corresponding textbox and the minipicker
- `miniSliderInput` is triggered when the value of the minipicker slider changes: it updates all the sliders and the minipicker spectrum canvas
- `movePickerIcon` is called when the position of the minipicker cursor changes: it updates all the other components accordingly and moves the other icons, if needed
In order to change the colour of the sliders, the function `getSliderCSS` is used to create a string that contains the style data necessary to update the gradient of a slider.

Changing the colour harmony from Mono to anything else triggers the creation of more cursors on the minipicker, which are used to show a preview of the other colours: the function `getSelectedColours` can be used to retrieve all the currently selected colours.

## TODO:
- Make the code more modular, avoid global variables and isolate the picker into a single class / module
- Refactor the code to be a bit cleaner
