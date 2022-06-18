# dtp-card

A.K.A. **D**ev**T**erm **P**rinter **Card** Maker

## Why

I want to create a little service that listens and prints out cards for things I want to remember throughout the day. I intend to make it available via a simple `curl` script in my shell and editors.

## Working Image Examples

Either copy the following image or try out the script in [p5.js](https://editor.p5js.org/) yourself. You can then try printing it with: 

`lp -d devterm_printer -o fit-to-page -o media=Custom.57x81mm -o scaling=100 ${PATH_TO_IMAGE}`

![An example card with a grey background, underlined header and main text body. The header reads: this is a card. The main text reads: There is text inside of the card. As you can see, it wraps. The final version using Go Graphics (gg) should match this general appearance. The ability to grow vertically would also be cool!](https://vcvcvc-dev.us-east-1.linodeobjects.com/400x300.png)

```javascript
/* Flash Card Generating Script for DevTerm using p5.js */

function setup() {
  createCanvas(400, 400);
}

const HEADER = "this is a card";
const FULL_TEXT = "There is text inside of the card. As you can see, it wraps. The final version using Go Graphics (gg) should match this general appearance. The ability to grow vertically would also be cool!";

const drawHeader = () => {
  textSize(40);
  text(HEADER, 20, 50);
  line(20, 54, 380, 54);
};

const drawText = () => {
  textSize(22);
  text(FULL_TEXT, 20, 70, 380)
};

function draw() {
  background(230);

  drawHeader();
  drawText();
}
```
