# LED Circular Clock

This project is a simple implementation of a circular LED clock using HTML/CSS/JavaScript. The clock displays the current time and highlights the seconds with animated LED dots.

## Features

- Circular LED display
- Current time displayed in HH:MM format
- Animated LED dots that light up according to the current seconds
- Responsive design that adapts to different screen sizes

## Technologies Used

- HTML
- CSS
- JavaScript

## Getting Started

### Prerequisites

You only need a web browser to run this project.

### Installation

1. **Clone the repository** (if using Git):
   ```bash
   git clone https://github.com/heavyagain/Horloge2Radio
   ```

2. **Open the `horloge.html` file** in your preferred web browser.

### Usage

When you open the `horloge.html` file, you will see a circular LED clock displaying the current time. The dots around the circle will light up based on the current seconds.

## Code Overview

- The HTML structure contains a main div for the clock and displays for the time and seconds.
- CSS is used to style the clock, the circular LED display, and the dots representing seconds.
- JavaScript is responsible for creating the LED dots and updating the clock every second.

### Key Code Snippets

**HTML Structure:**
```html
<div class="clock">
    <div class="led-circle" id="ledCircle"></div>
    <div class="led-display">
        <div id="timeDisplay">00:00</div>
        <div id="secondsDisplay">00</div>
    </div>
</div>
```

**JavaScript for Clock Update:**
```javascript
const updateClock = () => {
    const now = new Date();
    const [hours, minutes, seconds] = [
        String(now.getHours()).padStart(2, '0'),
        String(now.getMinutes()).padStart(2, '0'),
        String(now.getSeconds()).padStart(2, '0')
    ];
    document.getElementById('timeDisplay').textContent = `${hours}:${minutes}`;
    document.getElementById('secondsDisplay').textContent = seconds;

    document.querySelectorAll('.led-dot').forEach((led, index) => {
        led.classList.toggle('active', index <= now.getSeconds());
    });
};
```

## Contribution

Feel free to submit issues or pull requests if you have suggestions or improvements for this project!

## License

This project is open-source and available under the [MIT License](LICENSE).
