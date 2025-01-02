# [Drumkit Webpage 🎶](https://drum-kit-seven-chi.vercel.app/)

This project is a simple and interactive webpage that simulates a drumkit. Users can play drum sounds by either clicking on the drum buttons displayed on the webpage or by pressing specific keys on their keyboard.

---

## Features

- **Interactive Drum Sounds**:
  - **Mouse Interaction**: Click on any of the drum buttons to play the corresponding sound.
  - **Keyboard Interaction**: Press the associated key (`w`, `a`, `s`, `d`, `j`, `k`, or `l`) to trigger the same sound.

- **Visual Feedback**:
  - When a drum sound is played, the corresponding button gets highlighted momentarily for visual feedback.

---

## How It Works

1. **Event Listeners**:
   - The script identifies all elements with the `.drum` class and adds event listeners:
     - **Click Events**: Play the corresponding sound when a button is clicked.
     - **Keydown Events**: Play the corresponding sound when a specific key is pressed.

2. **Sound Mapping**:
   - Each drum is mapped to a specific key and a sound file:
     - `w`: Crash
     - `a`: Kick Bass
     - `s`: Snare
     - `d`: Tom-1
     - `j`: Tom-2
     - `k`: Tom-3
     - `l`: Tom-4

3. **Sound Playback**:
   - When a drum button is clicked or a key is pressed, the corresponding sound is played using the `Audio` object.

4. **Button Animation**:
   - A CSS class `pressed` is added to the active button to provide visual feedback.
   - The class is removed after 200ms using `setTimeout`.

---

## Key Files

- **`index.html`**:
  - The structure of the webpage, including the drum buttons.

- **`style.css`**:
  - Styles for the drumkit, including the animation for button presses.

- **`index.js`**:
  - JavaScript code that handles user interactions and sound playback.

- **`sounds/`**:
  - Folder containing audio files for the drum sounds (`crash.mp3`, `kick-bass.mp3`, etc.).

---

## Technical Details

### JavaScript Logic:

1. **Adding Event Listeners**:
   - The script dynamically determines the number of drum buttons using `document.querySelectorAll(".drum").length`.
   - Adds `click` and `keydown` event listeners to trigger drum sounds.

2. **Sound Playback**:
   - Sounds are mapped to keys using a `switch` statement:
     ```javascript
     switch (key) {
         case "w":
             var audio = new Audio("sounds/crash.mp3");
             audio.play();
             break;
         // Other cases...
     }
     ```

3. **Animation**:
   - The `animation` function adds a `pressed` class to the active button:
     ```javascript
     function animation(key) {
         document.querySelector("." + key).classList.add("pressed");
         setTimeout(function() {
             document.querySelector("." + key).classList.remove("pressed");
         }, 200);
     }
     ```

---

Enjoy creating music with the Drumkit Webpage! 🥁🎶
