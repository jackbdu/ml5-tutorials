# Machine Learning for Absolute Beginners (with ml5.js)

## Introductions

- Overview
  - What is [ml5.js](https://ml5js.org) and [ml5-next-gen](https://github.com/ml5js/ml5-next-gen/)?
    - Why ml5.js?
    - What is [tensorflow.js](https://www.tensorflow.org/js)?
    - Why JavaScript?
  - What is [p5.js](https://p5js.org/)?
    - Why p5.js?
  - p5.js and ml5.js examples
    - [ml5.js community page](https://ml5js.org/community)
    - [p5.js showcase page](https://showcase.p5js.org/)
    - [Daily Sketches (2022)](https://jackbdu.com/works/daily-sketches/)

## p5.js Basics

- [p5.js Web Editor](https://editor.p5js.org/)
  - Creating an account
    - Saving sketches
    - Saving settings
      - Theme
      - Text size
      - Autosave
      - Autoclose Brackets and Quotes
      - Autocomplete
  - Code editor
    - `setup()` & `draw()`
  - Run code
  - Preview
    - Webpage
    - Canvas
  - Give sketch a name and save it

- Take a look at the template
  - `createCanvas()`
    - Change size
  - `background()`
    - Change color

- Write our own code
  - Drawing a circle
    - `circle()`
      - `x`, `y`, `d`
    - Other shapes
      - [p5.js reference page](https://p5js.org/reference/)
  - Drawing a circle with variables
    - `let` & `const`
  - Making the circle move
    - `+=` & `-=`
    - `++` & `--`
  - Making the circle interactive (special variables)
    - `mouseX` & `mouseY`
    - Putting `background()` in `draw()` vs in `setup()`
  - Drawing circles at random positions
    - `random()`
      - Specifying maximum value for `random()`
      - `width` & `height`
  - Drawing circles with random colors
    - `fill()` & `noFill()`
    - `stroke()` & `noStroke()`
    - Specifying both minimum and maximum values for `random()`

- Exercise
  - Draw random shapes
    - `if` statements
    - Specifying an list (array) of choices (elements) for `random()`
      - `['circle', 'square']`
