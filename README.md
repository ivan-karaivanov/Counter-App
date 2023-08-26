# JavaScript Click Counter Program

This is a simple JavaScript program that allows you to increment, decrement, and reset a counter using buttons. The program also changes the color of the counter based on its value.

## How it Works

The program uses JavaScript to interact with an HTML document. It selects the necessary elements from the HTML using class names and adds event listeners to the buttons. Here's a breakdown of the main components of the program:

- `const count = document.querySelector(".count");`: This line selects the HTML element with the class "count", which is where the counter value is displayed.

- `const buttons = document.querySelector(".buttons");`: This line selects the HTML element with the class "buttons", which contains the buttons for incrementing, decrementing, and resetting the counter.

- `buttons.addEventListener("click", (e) => { ... });`: This event listener is added to the "buttons" element. It listens for clicks on any element inside the "buttons" element.

  - Inside the event listener, the program checks which button was clicked using `e.target.classList.contains("add")`, `e.target.classList.contains("subtract")`, and `e.target.classList.contains("reset")`.

  - If the "Add" button is clicked, the counter value is incremented and the `setColor()` function is called.
  - If the "Subtract" button is clicked, the counter value is decremented and the `setColor()` function is called.
  - If the "Reset" button is clicked, the counter value is set to 0 and the `setColor()` function is called.

- `function setColor() { ... }`: This function sets the color of the counter text based on its value. If the counter value is greater than 0, the color is set to yellow. If the counter value is less than 0, the color is set to orange. Otherwise, the color is set to white.

## Usage

1. Include the following HTML code in your document to define the counter and buttons:

```html
<div class="count">0</div>
<div class="buttons">
  <button class="add">Add</button>
  <button class="subtract">Subtract</button>
  <button class="reset">Reset</button>
</div>
```

2. Add the JavaScript code in your script file or `<script>` tag:

```javascript
const count = document.querySelector(".count");
const buttons = document.querySelector(".buttons");

buttons.addEventListener("click", (e) => {
  if (e.target.classList.contains("add")) {
    count.innerHTML++;
    setColor();
  }
  if (e.target.classList.contains("subtract")) {
    count.innerHTML--;
    setColor();
  }
  if (e.target.classList.contains("reset")) {
    count.innerHTML = 0;
    setColor();
  }
});

function setColor() {
  if (count.innerHTML > 0) {
    count.style.color = "yellow";
  } else if (count.innerHTML < 0) {
    count.style.color = "orange";
  } else {
    count.style.color = "#fff";
  }
}
```

3. Open your HTML file in a web browser. You will see the counter and buttons. Click the buttons to interact with the counter and observe how the value changes dynamically.

## License

This program is open-source and available under the [MIT License](LICENSE).
