# Introduction
## Project Name : tictactoe
Tic-tac-toe is a classic game typically played by two players, often referred to as "X" and "O," who take turns marking spaces in a 3x3 grid. The objective of the game is to be the first to get three of your marks in a horizontal, vertical, or diagonal row.

Here are the basic rules:

1. The game is played on a grid that's traditionally 3 squares by 3 squares. <br>
2. Players take turns marking a space in the grid with their symbol (X or O). <br>
3. The first player to get three of their symbols in a row (horizontally, vertically, or diagonally) wins the game. <br>
4. If the grid is filled and neither player has achieved a winning combination, the game is a draw. <br>
## Link :
## Summary of Issue examined :
The summary of this issue is to enhance the tic-tac-toe game by adding two new features:

* Save Winning Score: Implement functionality to save the winning scores of players. 

* Save User-Selected Theme: Allow users to select a theme for the game interface and save their preference. This feature enables players to customize the appearance of the game according to their preferences or mood.
## Detailed discussion of issues examined to :
I worked on the issue to save the winning score and to save the user selected theme. For the first part, there are various methods to solve this issue such as 
* Cookies
* Local Storage
* Session Storage
* IndexedDB <br>
from the above issues, I used the local storage method to solve this issue. Local storage allows you to store data with no expiration date. It remains even after the browser is closed and reopened. You can use the localStorage object to set and retrieve values.
# Code  
## index.html
Add high score label
``` javascript
<h5>Highest Score:<span id="highestScore">0</span></h5>
```
Assign the light mode value to theme 
```javascript
darkToggle[1].textContent = "Light Mode";
     updateTheme("black");
```
Assign the dark mode value to theme 
```javascript
darkToggle[1].textContent = "Dark Mode";
     updateTheme("white");
```
## app.js
Add listner on page load
```javascript
/* Score update logic */

document.addEventListener("DOMContentLoaded", function() {
    // Retrieve the highest score from local storage, if it exists
    var highestScore = localStorage.getItem('highestScore');
    if (highestScore) {
        document.getElementById('highestScore').textContent = highestScore;
    } else {
        // If the highest score is not found in local storage, initialize it with a default value
        localStorage.setItem('highestScore', 0);
    }

    //  creating values for theme 
     //localStorage.setItem('themeName', "white");
     if(localStorage.getItem('themeName') == "black")
     {
        myFunction();
     }
});
```
Update Highest Score
```javascript
// Example usage: Call updateHighestScore() whenever a new high score is achieved
// For example, assuming you have a function called 'updateScore' that updates the score display
// Update highest score
function updateHighestScore(newScore) {
    var currentHighestScore = parseInt(localStorage.getItem('highestScore'));
    currentHighestScore += newScore;
    localStorage.setItem('highestScore', currentHighestScore);
    document.getElementById('highestScore').textContent = currentHighestScore;
}
```
Update Theme
```javascript
// update Theme
function updateTheme(themeColor) {
    localStorage.setItem('themeName', themeColor);

}
```
Call to update score <br>
Here, in checkWinner(), I make a call to ``` javascript updateHighestScore(10); ``` function.

# Reference :
Reference regarding local storage method: https://blog.logrocket.com/localstorage-javascript-complete-guide/
