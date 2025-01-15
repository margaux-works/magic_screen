# Magic Screen

Magic Screen is a web-based implementation of the classic Etch A Sketch toy. This project allows users to create colorful sketches using the arrow keys and reset the canvas with a shake effect. It's built using HTML, CSS, and vanilla JavaScript.

---

## Live Demo

You can view the live project hosted on GitHub Pages here:
[Magic Screen](https://margaux-works.github.io/magic-screen/)

---

## Features

- **Interactive Drawing**: Use the arrow keys to draw lines on the canvas.
- **Dynamic Colors**: The drawing color cycles through hues, creating a rainbow effect.
- **Shake to Clear**: Clear the canvas by clicking the "Shake!" button, which triggers a shake animation.

---

## Screenshots

![Screenshot of main view](/screenshot-magic-screen.png)

---

## Technology Stack

- **HTML**: Markup structure for the page.
- **CSS**: Inline styling for aesthetics and animations.
- **JavaScript**: Handles drawing logic, keyboard interactions, and animations.

---

## Installation

To run the project locally:

1. Clone this repository:

   ```bash
   git clone https://github.com/margaux-works/magic-screen.git


   ```

2. Navigate to the project directory:

   ```bash
   cd magic-screen

   ```

3. Open the index.html file in your browser.

---

## Usage Instructions

1. Open the project in your browser.
2. Use the arrow keys to draw on the canvas.
3. Click the "Shake!" button to clear the canvas and start again.

---

## Code Highlights

### Main Drawing Logic

The draw function handles line drawing on the canvas and dynamically changes the color:

```javascript
function draw({ key }) {
  hue += 10;
  ctx.strokeStyle = `hsl(${hue},100%,50%)`;
  ctx.beginPath();
  ctx.moveTo(x, y);
  switch (key) {
    case 'ArrowUp':
      y -= MOVE_AMOUNT;
      break;
    case 'ArrowRight':
      x += MOVE_AMOUNT;
      break;
    case 'ArrowDown':
      y += MOVE_AMOUNT;
      break;
    case 'ArrowLeft':
      x -= MOVE_AMOUNT;
      break;
  }
  ctx.lineTo(x, y);
  ctx.stroke();
}
```

### Shake Effect

The clearCanvas function clears the canvas and triggers a shake animation:

```javascript
function clearCanvas() {
  canvas.classList.add('shake');
  ctx.clearRect(0, 0, width, height);
  canvas.addEventListener(
    'animationend',
    () => {
      canvas.classList.remove('shake');
    },
    { once: true }
  );
}
```

## Acknowledgments

This project is a practice exercise from the [JavaScript Course](https://beginnerjavascript.com/) by **Wes Bos**.

---

## License

This project is open source and available under the [MIT License](LICENSE).
