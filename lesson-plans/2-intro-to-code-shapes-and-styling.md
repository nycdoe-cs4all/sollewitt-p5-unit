# 2: Intro to Code, Shapes and Styling

### Teacher Notes and Overview

* Utilize ICM early units
* Introduce p5 editor
* Introduce shapes - circles, rects, lines, points.
  * Include other shapes as alternate extension???
* Introduce color/styling simultaneously
  * A little more rapid fire
* Activity for end of lesson...?????

### Objectives

Students will be able to:

* Create new sketches in the p5 editor
* Adjust canvas size and background color
* Draw basic shapes - circles, rectangles, lines, and points.
* Utilize the reference sheet

### Suggested Duration



### NYS Standards



### Vocabulary

* **p5.js**
* **code**
* **IDE**
* **function**

### Planning Notes and Materials



### Resources

* [JavaScript in 100 Seconds](https://youtu.be/DHjqpvDnNGE?si=THVxyUc\_J1oz9Pk-) (Youtube Video)
* [What is p5.js?](https://www.codecademy.com/learn/learn-p5js/modules/p5js-introduction-to-creative-coding/cheatsheet) (Codecademy Additional Resource)
* [p5 Reference Sheet](https://p5js.org/reference/) (p5 Website)
* [p5 Grid Worksheet](https://drive.google.com/file/d/1CFJLhiHEBTQPxqTaNxESPxpc7F0Yto4D/preview) (PDF Worksheet)
* [Desmos p5 Coordinate Grid Tool ](https://www.desmos.com/calculator/o75y8av9jw)(Optional Resource)
* [Lesson 1, Part 1 Starter Code](https://editor.p5js.org/cmorgantywls/sketches/jEnw7jo9m) (p5 Editor)

### Assessments

**Formative:**

**Summative:**

### Do Now/Warm Up (\~3 min - 5 min)

Ask students to navigate to the [p5 editor website](https://editor.p5js.org/) and create an account.&#x20;

{% embed url="https://editor.p5js.org/" %}

_Note that due to DOE settings, if they are signing up with a DOE (@schools.nyc.gov) email, they will **not** be able to use the 'Sign Up with Google', 'Sign in with Google', or any other SSO option. They must manually type their email address and password._

### Intro: Your First p5 Sketch (\~10 - 15 minutes)

Explain to students that for this unit, they will be learning to use p5.js, which is a library that builds onto the JavaScript programming language. You may or may not want to show them the brief video on JavaScript or other resources linked in the above [Resource](2-intro-to-code-shapes-and-styling.md#resources) section, depending on how much prior coding experience they may or may not have.

p5.js and it's Java equivalent, Processing, are both libraries used for creative coding and by artists such as [Casey Reas](https://reas.com/).

We will be coding in the p5 editor, which students made an account for in the Do Now. This is an example of an online IDE - integrated development environment - which is a place where people write code.

To get us started, we will work off the same sketch together in a _code along_ - this is when a teacher demonstrates code on the screen and students - spoiler alert - code along. This code along will be a mix of teacher led information and student information.

Ask students to duplicate the [starter code](https://editor.p5js.org/cmorgantywls/sketches/jEnw7jo9m). Please note that they will need to manually hit save - this is a huge sticking point for students who did not grow up having to do this! Remind them to save when they first duplicate and often thereafter.

Begin by introducing students to the code - they can hit play if they want to see the results. At the top, there is a code comment that begins with `//`. All code comments in JavaScript will begin that way - comments will not be read by the computer and are just for us to see.

Next, note that there are two big **functions** here  - setup and draw. These are foundational to making p5 sketches run and we always need them. Note for students the `{ }` curly braces - these are important in our code as it shows the computer where certain things begin and end. In this case, we can see setup begins on line 3 and ends on line 5 (putting your cursor by one brace will highlight the other). The draw function begins on line 7 and ends on line 12. Adding things to one of these functions means putting it between the curly braces.

Outside of the setup and draw, we have other functions inside of these functions that make things happen on our screen. We know we are dealing with a function because it will always be a word with `()` after it - these `()` may or may not hold _arguments_ which are values that change how the function runs.

Let's examine these functions from the top down and determine what they do. Begin with `createCanvas(400, 400)`. Ask students to change each number to a different value, one at a time, hitting the play button after each change. They should keep changing the values until they think they can explain what each does, and then they should leave that as a comment.  Allow \~30 seconds - 1 minute of play time and then review together - ensure students have something like:

```javascript
createCanvas(400, 400) //first num width, second num height of canvas
```

Reset the values back to 400, 400 or something else that is a decent size before continuing into draw and repeating htis process for the 3 functions there. First, direct students to adjust the values in background and fill. Same as before, they should adjust one number at a time, hit play, and then adjust the other. Note that each of these has a maximum value of 255. Once students think they know what each controls, have them leave a comment. After \~30 seconds - 1 minute of play, reconvene to make sure they have something like:

```javascript
function draw() {
  background(220) //max value 255, background color of canvas, low numbers dark, high numbers light
  
  fill(255) //max value 255, color of ellipse, low numbers dark, high numbers light
  ellipse(150, 200, 50, 75)
}
```

Finally, we've reached the ellipse. This function has _four_ arguments. Once again, they should change each number **one at a time** and hit play after each change until they understand what each number does and can leave it as a comment. This may require slightly longer to do - allow \~2 minutes before reconvening to discuss:

```javascript
function draw() {
  background(220) //max value 255, background color of canvas, low numbers dark, high numbers light
  
  fill(255) //max value 255, color of ellipse, low numbers dark, high numbers light
  ellipse(150, 200, 50, 75) //left/right position, up/down position, width, height
}
```

### Introducing: the Reference Sheet && p5 Grid (\~5 - 10 minutes)

Students were able to figure e
