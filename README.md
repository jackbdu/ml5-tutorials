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

## ml5.handPose

- handPose examples
  - [Writing with hand](https://www.instagram.com/p/CyuxLEPA136/)
  - [Camera following hand](https://www.instagram.com/p/Cy4ZKwnrL_b/)
  - Interactive melody with [mouse](https://www.instagram.com/p/C4KnkS_uIkg/) vs [hand](https://www.instagram.com/p/C4WozrtsZ4r/)

- Working with webcam
  - Bare minimum
    - `createCapture(VIDEO)`
      - See `<video>` appear outside canvas
    - `image()`
      - Defining variables in the global scope (outside `setup()` and `draw()` functions) for sharing between `setup()` and `draw()`
      - See video appear on canvas
  - Tinkering
    - `createCanvas(640, 480)`
    - `video.size()`
      - Reviewing `width` & `height`
      - See `<video>` size changes
    - Resizing video with `image()`
      - `<video>` size remains
      - handPose uses `<video>` as the reference
    - `video.hide()`
- Adding ml5.js library
  - Sketch Files
    - sketch.js
    - style.css
    - index.html
      - HTML tags come in pairs
        - `<head></head>` & `<body></body>`
        - `<script></script>` tags
            - Identifying `<script>` for p5.js within `<head>` and `</head>`
            - Add `<script>` for ml5.js
               - `<script src="https://unpkg.com/ml5@0.20.0-alpha.3/dist/ml5.js"></script> `

- handPose basics
  - In `preload()`
    - `handPose = ml5.handPose();`
  - In `setup()`
    - `handPose.detectStart(video, function() {})`
      - `console.log(’hand detected’)`
      - callback functions
        - `function(){}` vs `gotHands`
  - `gotHands(results)`
    - `console.log(results)`
    - `hands = results`
  - `draw()`
    - `if` statements
      - `if (hands !== [])`
      - `if (hands.length > 0)`
    - array
      - `hands[0]`
        - `console.log(hands[0])`
      - `hands[0].index_finger_tip`
    - Draw circle at index finger tip
    - Apply to more than one hand
      - `for` loops
        - `for (const hand of hands)`
        - Display all keypoints
          - `for (const keypoint of hand.keypoints)`
        - Display keypoint indices
          - `for (const i = 0; i < hand.keypoints.length; i++)`
          - `text()`

- Exercise
  - Draw something between two hands
  - `if (hands.length >= 2)`
  - `hands[0]` and `hands[1]`
