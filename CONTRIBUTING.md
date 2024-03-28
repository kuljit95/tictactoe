# Introduction 
## Project Name : tictactoe
Tic-tac-toe is a classic game typically played by two players, often referred to as "X" and "O," who take turns marking spaces in a 3x3 grid. The objective of the game is to be the first to get three of your marks in a horizontal, vertical, or diagonal row.

Here are the basic rules:

1. The game is played on a grid that's traditionally 3 squares by 3 squares. <br>
2. Players take turns marking a space in the grid with their symbol (X or O). <br>
3. The first player to get three of their symbols in a row (horizontally, vertically, or diagonally) wins the game. <br>
4. If the grid is filled and neither player has achieved a winning combination, the game is a draw. <br>
## Link : https://github.com/kuljit95/tictactoe/edit/Kujit-dev-AudioSlider/CONTRIBUTING.md
## Summary of Issue examined : https://github.com/yelynn1/tictactoe/issues/60
The summary of this issue is to enhance the tic-tac-toe game by adding the volume slider. A volume slider for music is a user interface component that allows users to adjust the volume of music playback. It typically consists of a horizontal bar (slider) that users can drag or click to change the volume level.
A volume slider for music provides users with a convenient way to control the audio output level, allowing them to personalize their listening experience according to their preferences and environmental conditions.
## Detailed discussion of issues examined to :
I worked to make the documentation to solve this issue which is described as follows: 

### HTML Code
1. Create the Audio Player:
  ```javascript
<audio id="myAudio" controls>
  <source src="your-audio-file.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
```

2. Craft the Volume Slider:
```javascript
<input type="range" min="0" max="1" step="0.01" id="volume-slider" />
```
This code creates a slider with:

type="range": Specifies a range input element.
* min="0" max="1": Sets the volume range from 0 (mute) to 1 (full volume).
* step="0.01": Allows fine-grained adjustments with 0.01 increments.
* id="volume-slider": Identifies the slider for JavaScript interaction.

### javaScript Code 
Get references to the audio element and the volume slider
```javascript
const audio = document.getElementById('myAudio');
  const volumeSlider = document.getElementById('volumeSlider');
```
Function to change the volume of the audio element
```javascript
function changeVolume() {
    // Set the volume of the audio element based on the slider value
    audio.volume = volumeSlider.value;
  }
```
Add an event listener to the volume slider
```javascript
 volumeSlider.addEventListener('input', changeVolume);
```
