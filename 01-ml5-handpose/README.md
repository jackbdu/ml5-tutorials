# ml5.handPose

We are going to start our ml5.js journey with pretrained models. Pretrained models are machine learning models that are trained to perform a specific task. In this chapter, we are going to learn how to use `handPose`, a pre-trained model that recognizes and hands in images and provides us with a list of coordinates of key features of each hand.

Before we start, let's take a look at a few of my sketches incorporating `handPose` to get an idea of what it is capable of.

  - [Writing text on screen with hand](https://www.instagram.com/p/CyuxLEPA136/)
  - [Camera zooming-in and following hand](https://www.instagram.com/p/Cy4ZKwnrL_b/)
  - [Drawing melodies with hand](https://www.instagram.com/p/C4WozrtsZ4r/)

## Webcam Setup

In this tutorial, we are going to track our hand pose in real-time with a webcam. Let's start by learning how to work with a webcam in p5.js.

In order to get a video feed from our webcam, we need to use the [`createCapture()`](https://p5js.org/reference/#/p5/createCapture) function. This function supports both capturing video and audio. Since we are only going to be working with video, we need to pass in `VIDEO` as an argument. Variables that are all caps like `VIDEO` are another kind of "speical" variables that p5.js provides for specific scenarios like this. Whenever we enter a keyword that is a part of the p5.js library, the Web Editor recognizes it and highlight it in a different color. This is one way we can tell whether or not we typed the keyword correctly.

```javascript
function setup() {
  createCanvas(400, 400);
  createCapture(VIDEO);
}

function draw() {
  background(220);
}
```
- handPose examples
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
