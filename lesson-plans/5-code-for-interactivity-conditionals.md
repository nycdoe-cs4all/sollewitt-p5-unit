---
description: How can I use control flow to change the behavior of my code?
---

# 5: Code for Interactivity: Conditionals

### Teacher Notes and Overview

This lesson introduces the most complex projects students will make thus far - those that rely on conditionals to change behavior of a program based on if certain conditions are met or not. For the purposes of this unit and setting, this lesson is designed as a crash-course. If you would like to delve deeper, we recommend exploring these lesson plans from our Introduction to Computational Media curriculum:

* [U2LA1.1: Conditionals and If/Else Statements](https://cs4all-icm.gitbook.io/js-intro-to-computational-media-2.0/unit-2-respond-and-draw-on-canvas/u2la1.1-conditionals-and-if-statements)
* [U2LA1.2: Conditionals and if, else if, and else statements](https://cs4all-icm.gitbook.io/js-intro-to-computational-media-2.0/unit-2-respond-and-draw-on-canvas/u2la1.2-conditionals-and-if-else-if-and-else-statements)
* [U2LA1.3: Logical Operators And/Or](https://cs4all-icm.gitbook.io/js-intro-to-computational-media-2.0/unit-2-respond-and-draw-on-canvas/u2la1.3-logical-operators-and-or)

### Objectives

Students will be able to:

* Understand conditional logic within real-world and programmatic examples
* Code conditionals to change appearance of objects on canvas

### Suggested Duration

1-2 Periods

### NYS Standards

\[COMING SOON]

### Vocabulary

* **Conditional statements** - is a set of rules performed if a certain condition is met
* **Else** - the second half of a conditional statement covers every outcome not specified in “if” &#x20;
* **Boolean expressions** - is a logical statement that is either TRUE or FALSE
* **Relational operators** - < , > , >=, <=, && (and), || (or)
* `&&` - **AND** - joins two statements to make sure they are both true before the whole statement is true
* `||` - **OR** - joins two statements so that if one is true, the whole statement is true

### Planning Notes and Materials

There are no specific planning notes or material needs, but it is worth previewing all the resources and extras to ensure you are prepared to teach this content as it is a little less forgiving than past lessons.

### Resources

* Video tutorial: [Conditional Statements](https://www.youtube.com/watch?v=1Osb\_iGDdjk)&#x20;
* [Conditionals On the Canvas ](https://youtu.be/IsJ4D-2TR8c)(Youtube Video) | Starter Code  ([p5 editor](https://editor.p5js.org/cmorgantywls/sketches/B0KjtW4yo) | [repl.it](https://replit.com/@qrtnycs4all/U2LA12-Conditionals-on-the-Canvas#script.js))
* Video tutorial: [Else, and else if, AND and OR ](https://www.youtube.com/watch?v=r2S7j54I68c)
* [And/Or In Code ](https://youtu.be/8TGpiFZ5gsY)(Youtube Video) | Starter Code ([p5 editor ](https://editor.p5js.org/cmorgantywls/sketches/6Ta8mC-DJ)| [repl.it](https://replit.com/@qrtnycs4all/U2LA13-AndOr-Starter-Code#script.js))
* Video tutorial: [Else, and else if, AND and OR](https://www.youtube.com/watch?v=r2S7j54I68c)

### Assessments

**Formative:**

Code Along Tasks

Exit Slip

**Summative:**

Upcoming Mini Project

Upcoming FInal Project

### Do Now/Warm Up (\~7 min - 12 min)

Distribute the [Pseudocode Conditional Worksheet](https://docs.google.com/document/d/1YPoLb9IEiLTQLOl2bu2JtVLNOOg0KTbmq\_x0g64UHPc/copy) to students. Ask them to fill out just the first column, and if necessary, offer suggestions for the first example to get them started. The rest they should be able to complete on their own. Ask them to, for now, ignore the second column.

After students have had time (\~3-5 minutes) to work on the first column, ask for some student shares, and then explain how you complete the second column by putting the plain English conditionals they’ve written into pseudocode.

Give students another \~5 minutes to complete the second column after you’ve given an example, and then review briefly before using this to launch into the coding portion of the lesson. For example:

|                    Action                    |                                         If/Else Statement                                        |                                                                                                      Pseudocode                                                                                                      |
| :------------------------------------------: | :----------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| **ACTION**: Go to the park with your friends | If (the weather is nice), then (I go to the park with my friends), else (I watch netflix inside) | <p><code>if(the weather is nice){</code> </p><p><code>I go to the park with my friends</code> </p><p><code>}</code> </p><p><code>else {</code> </p><p><code>I watch Netflix inside.</code> </p><p><code>}</code></p> |

Give students another \~5 minutes to complete the second column after you’ve given an example, and then review briefly before using this to launch into the coding portion of the lesson.

It is important that students understand that an expression will evaluate to true or false. Then the computer will perform an action based on the given condition. Some students may ask where the words true and false words actually appear but tell them that the words are actually activation signals that the computer can only see - much like a light's on/off switch, we only see the word if we choose to print it, which we can do in some examples!

We want the computer to look at an expression and evaluate whether it is true or false, if it's true do one thing, and if it's false do another. Let's take a look at some expressions and evaluate them as true or false.

* `26>5` → 26 is greater than 5. Let's read that as a question. Is 26 greater than 5? Yes it is. This expression evaluates to "true."
  * If we wanted to test this in our editor, we could enter `console.log(26>5)` at the top of our program. Hit play, and we should see 'true' in the console!
* `10==14` → Since 10 is not equal to 14, this expression evaluates to "false"&#x20;
  * Try entering `console.log(10==14)` in a program. You should get 'false' in the console!
* `4>210` → This expression is also "false"&#x20;
  * Try entering `console.log(4>210)` in a program. You should get 'false' in the console!
* `2==2` → "true"
  * Try entering `console.log(2==2)` in a program. You should get 'true' in the console!

These "greater than" or "less than" signs are relational operators - they compare two numbers, which is what we're going to do in our first conditional statement.

We have many ways to compare things in code that students should be aware of - they're useful to have posted somewhere in the room:

* \== the same as&#x20;
* != not the same as
* **<** greater than&#x20;
* <= greater than or equal to&#x20;
* < less than&#x20;
* <= less than or equal to

The boolean expression inside the parentheses is the expression being evaluated. If the expression is true, then the computer will execute the code inside the curly brackets. If it evaluates to false, the code is not run and the program will continue with the code that follows the expression.

```javascript
if(5<6){
    background(0)
} //background will turn black since 5 IS less than 6.

if(5<4){
    background(0)
} //background will not be black because 5 IS NOT less than 4. Code will be skipped!
```

### Our First Conditional (\~12 - 15 minutes)

It's time to begin coding our first conditional! Bring students together for a code along. In a new project, create a shape on the screen with a variable to hold its color - this is a slightly new skill that we are sneaking in. Remind students how to declare, initialize, and use a variable, and then how to change the color variable in a conditional.

The conditional we will be building will make the color of the shape change when the mouse is on one side of the screen, and change back when the mouse is on the other side of the screen.

To do this, we will have an `if` statement that controls what should happen _if_ a certain condition is met - we covered this in the Do Now. But we will also utilize an `else` statement, which will tell the computer what to do if the condition is _not_ met. Note that `else` does not have a boolean expression associated with it as it is covering for _all other possible scenarios._&#x20;

```javascript
let circColor

function setup(){
  createCanvas(400,400)
  circColor = color(255, 255, 0)
}

function draw(){
  background(220)
  fill(circColor)
  ellipse(200,200,100,100)

  if(mouseX>200){
    circColor = color(255, 0, 255)
  } //note the curly braces - these are important!
  else{
    circColor = color(255, 255, 0) //reset to original color
  } //note the curly braces - these are important!
  
}
```

Use `console.log(mouseX)` so that students can see how the condition in the if statement is satisfied. Move the mouse back and forth a few times so that the shape changes color when mouseX increases and decreases: our sketch is now interactive and responsive to the user moving the mouse!

### Student Challenge (\~15 minutes)

Once the code along is completed, ask students to do the following:

* Create a rectangle that will change height based on if the mouse is on the top or bottom of the screen
* Create a variable to hold the size of the circle. Change the size of the circle only if mouseX is at exactly 200, otherwise keep it the same.
* Create a variable to hold the color of the rectangle. Change the color of the rectangle only if mouseY is at exactly 200, otherwise keep it the same.
* Create a conditional that will change the color of the background when a specific condition is met. (You'll need a variable for background color!)
* Create a conditional that will make a new shape appear only when the mouse is in a certain position. No variables needed for this, as you'll be calling a shape function directly in your conditional statement.

As you code along through the other conditional examples ensure that students are:

* Commenting on their code. (Model examples for students as needed)&#x20;
* Using variables in the correct scope.&#x20;
* Using console.log() to debug and test&#x20;
* Saving their sketches with appropriate and clear titles.

Once they are done, ask students what else they could change about this shape or other things in the sketch, such as the background. Have them create variables and use them to change values of the shape itself when the mouse is in different positions, or create different shapes and variables to change with conditionals.

### Else If and Logical Operators (10 - 12 minutes)

_This is likely the start of the second day of your lesson sequence - if so you will utilize this beginning discussion as your intro activity and proceed from there!_

Yesterday, students learned about the conditional `if` / `else` statements - the shape was either one color when a condition was met, or it was another because the condition was not met. But sometimes we may want to check for more than one condition!

Explain to students the existence of the ‘else if’ statement and its purpose in a program. We can use "else if" to add more possible outcomes to our sketches. Since there are often more than two possible conditions that we want to work with, we can instruct the program to perform different tasks based on a range of conditions.

I might want to tell someone that if it's cold they should wear a coat, but I also may want to say:

* "if it's freezing, wear a coat,&#x20;
* if it's cold, wear a jacket,&#x20;
* otherwise just wear a sweater."&#x20;

Ask students to brainstorm on their own several more situations were _multiple_ conditions may need to be examined to make the right choice.

Then, explain how this would look in code:

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

The program will test each condition in order. As soon as one condition evaluates to true, the code inside those brackets is executed and the program continues after the statement.

Likewise, in addition to checking each condition one at a time, we can combine multiple conditions for the computer to check for at once using `and` and `or`. Consider these diagrams - how are they alike? How are they different? Under which conditions does José get ice cream?

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Make sure students understand the difference between `and` - where both conditions must be met - and `or` where only one condition must be met, but it can be either one. They will mostly be using `and` today, but these are useful programming tools they may want to investigate later!

### Code Along with Logical Operators (10 min)

Ask students to [open up the and/or starter code](https://editor.p5js.org/cmorgantywls/sketches/6Ta8mC-DJ). They should notice that it is a screen with two lines splitting it into four equal quadrants, and that the coordinates are displayed in the top left corner of the screen as they move the mouse around.

Students will be writing conditionals to change the background color when the mouse is in each different quadrant; note that the entire background will be changing, and not each individual quadrant, which can be a sticking point for students. Begin by asking students to explore the canvas, specifically moving their mouse into each quadrant and reporting what they notice about the x and y values when they are in each area.

You will be coding along the bottom right quadrant because it is the furthest from where the mouse starts when students hit play. Ask students what they notice about values in this quadrant specifically - they should recognize that all x values are greater than 200, and all y values are also greater than 200 (the lines represent the exact centers of each axis). Together, create the following code (you will need to make the bgColor variable):

```javascript
if(mouseX > 200 && mouseY > 200){
  bgColor = color(255,0,255)
}
```

From there, ask students to create else if conditionals for every other quadrant and an else statement to handle if the mouse is in the exact center of the screen. This can be a pair programming activity or done independently, based on the needs of your students. You can also have them complete work independently and then swap to read for comments/bugs/etc with a partner.

As students begin working, circulate to ensure:

* Commenting their code.&#x20;
* Using variables in the correct scope.&#x20;
* Using console.log() to debug and test&#x20;
* Saving their sketches with appropriate and clear titles.

### Wrap Up (5 minutes)

Students can submit code via a Google Form if you would like to collect it. If not, have students come back together for a discussion on what struggles they encountered in this activity.&#x20;

Students can also lead code-alongs or walk through their code with the class.

Guiding Questions

* What is a boolean statement?&#x20;
* What are the two responses I can get from a boolean statement?&#x20;
* What is a conditional statement and how can I use it in programming?&#x20;
* What was challenging about creating an interactive sketch with boolean and conditional statements? Why? How did you solve the challenge? What was easy?

### Extension and Addition

This is a crash course in conditionals; if you would like a deeper dive, consider exploring the lessons from Introduction to Computational Media linked in the lesson overview. They include exercises to practice conditional syntax off the canvas, and to look at pseudocode condtionals using DeltaMath.
