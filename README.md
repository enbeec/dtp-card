# dtp-card

A.K.A. **D**ev**T**erm **P**rinter **Card** Maker

## Why

I want to create a little service that listens and prints out cards for things I want to remember throughout the day. I intend to make it available via a simple `curl` script in my shell and editors.

## Requirements

- [ ] plain text HTTP service (LAN/VPN only)
- [ ] `/card/print?header=myHeader&fullText=someTextHereToPrint`
	- creates the card using `github.com/fogleman/gg`
	- rather than saving the file, just send it to `lp` for printing
	- JSON could end up being a good call but URL params
- [ ] `/card/help` returns usage info
- [ ] example client script using `sh` and `curl`
- [ ] BONUS: an `org-babel` example using [`ob-http`](https://github.com/zweifisch/ob-http)
- [ ] BONUS: a capture command in Emacs

## Working Image Examples

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
