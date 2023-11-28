# 3: Intro to Code, Variables

### Teacher Notes and Overview

* ICM resources
* Combine mouseX/mouseY with making variables
* Make shapes move on screen/follow the mouse (two circles - one as emoji?)
* Include random

### Objectives

Students will be able to:

* Use built-in system variables like `width`, `height`, `mouseX`, `mouseY`
* Create custom variables to hold values
* Utilize `random()` to generate random values

### Suggested Duration

2 class periods

### NYS Standards

\[COMING SOON]

### Vocabulary

* `width`
* `height`
* `mouseX`/`mouseY`
* `variable`
* `random()`

### Planning Notes and Materials



### Resources

* NEED: Do Now Starter Code
* [Robot Starter Code](https://editor.p5js.org/cmorgantywls/sketches/EJj7pcAx9) (p5 Editor)

### Assessments

**Formative:**

**Summative:**

### Do Now/Warm Up (\~3 min - 5 min)

Share students on this sample ([p5 editor ](https://editor.p5js.org/cs4all/sketches/S1eQDQRXX)| [repl.it](https://replit.com/@qrtnycs4all/U1LA21-Intro-to-Variables-Do-Now#script.js)) code.

Instruct students to play with their code and then try to create an ellipse that is perfectly centered in their canvas. If students complete this task early, ask them to make the ellipse large enough so that the ellipse touches each edge of the canvas (if their canvas is square - if it comes out as a rectangle, touching the top and bottom will suffice). **NOTE: **_**There is also an extra credit typo for them to fix in the code!**_

_While students struggle, teachers will circulate and identify one or two students who have completed the task to share their work. Plug their computer into the smartboard (or otherwise display their code) - hit play again and the canvas values should reroll, creating a new canvas in which the circle is not necessarily centered._

**Ask students:** Why was this process frustrating? Why are you mad that we hit play again?

Students should realize it was frustrating guessing the center and that hitting play again changed their design, thus ruining all of their hard work.

### Using System Variables (\~10 minutes)

When we want to be able to easily update our code, we may use _variables_ to hold value. We can make our own variables with our own values - which we will do later in the lesson - but it's also important to know that there are a number of built-in, system variables that p5.js already recognizes. A useful one for us here is `width`.

We can figure out this variable with a simple `console.log(width)` added to setup - what do we notice this value is if we run the program a few times? _Students should realize it represents the width of the canvas, which is changing because it is being assigned a random value in setup._

Ask students how they could use this to center the ellipse on the screen. Give them a moment to attempt, then review that they could write code that looks like:

```javascript
ellipse(width/2, 200, 50, 50)
//alternately, it could be height/2, which may be worth discussing with students.
```

Once students have this answer, ask them: could they make the ellipse be 1/3 of the way across the page? 1/4? Give time to explore before coming back together.

Now, explain to students that there are other system variables. Two of the most useful they will see are `mouseX` and `mouseY`. These display the current position of the mouse. In the draw function, add a `console.log(mouseX)` and then move the mouse around the screen so students can take note of the changing values.

Students should notice that these are just numbers, which means that variable can take the place of _anywhere we see a numeric value_. So, for example our ellipse could become:

```javascript
ellipse(width/2, mouseY, 50, 50)
```

Our ellipse should now move up and down with the mouse, while still saying centered on the x-axis! But again, we can use these variables to control _anything numeric_ - so let's add them to color:

```javascript
fill(mouseX, mouseY, 150)
ellipse(width/2, mouseY, 50, 50)
```

Encourage students to move their mouse around the screen and report back with the results.

### Student Challenges (\~10 min)

Ask students to complete as many of the following as possible in the next 10ish minutes:

1. Create a rectangle that moves left and right with the mouse.
2. Create an ellipse that is 2/3 across the page and changes color only when the mouse moves up and down.
3. Create an ellipse that is perfectly centered and changes size when the mouse moves (direction of your choice).
4. Create a rectangle in the lower right hand corner and has a `strokeWeight()` that changes as the mouse moves across the screen.
   1. **NB:** _The strokeWeight may get RIDICULOUSLY THICK here. Remind students that just as they divided width and height, they can also divide mouseX/mouseY to get a more limited range of results._
5. Create a shape of your choosing 1/4 of the way down the screen and 1/2 across that becomes _more transparent_ as the mouse moves up and down.

### Move Together Code Along (\~10 - 15 minutes)

Share students on the [robot starter code ](https://editor.p5js.org/cmorgantywls/sketches/EJj7pcAx9)and ask them to make a copy. Explain that we would like to use `mouseX` and `mouseY` so that the entire robot follows the mouse. Before they start coding, explain you want to test this on the board - if you make the head rectangle follow the mouse, everything else will stay. If you then make an eye follow the mouse, you'll notice an issue: it's not in the correct place anymore!\
\
This is because it's using the _exact same_ coordinates for each because they are each using `mouseX` and `mouseY`. We can fix this problem by offsetting our coordinates based on the distance they are apart. Let's first copy all of our robot code and make it a comment above our current code - we will use this as a reference for later:

```javascript
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
  text(mouseX + ", " + mouseY, 20, 20)
  //ORIGINAL robot head
  // rect(150, 150, 100, 75)
  // //eyes
  // ellipse(175, 179, 20, 20)
  // ellipse(223, 179, 40, 40)
  // //mouth
  // rect(160, 204, 80, 10)
  // //antennae
  // line(175, 150, 130, 100)
  // line(215, 150, 240, 110)
  
  //MOVING robot head
  rect(mouseX, mouseY, 100, 75) //original (150, 150)
  //eyes
  ellipse(175, 179, 20, 20)
  ellipse(223, 179, 40, 40)
  //mouth
  rect(160, 204, 80, 10)
  //antennae
  line(175, 150, 130, 100)
  line(215, 150, 240, 110)
  
}
```

Notice we used `mouseX` and `mouseY` in our head rectangle. We are using this as an anchor point or origin - this is the point that will follow or be on top of the mouse. Every other point will be in relation to this one by preserving the distance between the original rectangle and the other shape.

For example, let's tackle the first eye. It is positioned at (175, 179) but our original rectangle was at (150, 150). That means there is a distance of +25 between the x positions and +29 between the y positions. So our code could look like:

```javascript
//MOVING robot head
  rect(mouseX, mouseY, 100, 75) //original (150, 150)
  //eyes
  ellipse(mouseX + 25, mouseY + 29, 20, 20)
  ellipse(223, 179, 40, 40)
  //mouth
  rect(160, 204, 80, 10)
  //antennae
  line(175, 150, 130, 100)
  line(215, 150, 240, 110)
```

If we run the program and move the mouse around, we should notice that our head and eye are following the mouse _and_ have maintained their original spacing! Let's continue and do this for each shape, pausing each time to run the program and make sure it works:

```javascript
  rect(mouseX, mouseY, 100, 75) //original (150, 150)
  //eyes
  ellipse(mouseX + 25, mouseY + 29, 20, 20)
  ellipse(mouseX + 73, mouseY + 29, 40, 40)
  //mouth
  rect(mouseX + 10, mouseY + 54, 80, 10)
  //antennae
  line(mouseX + 25, mouseY, mouseX - 20, mouseY - 50)
  line(mouseX + 65, mouseY, mouseX + 90, mouseY - 40)
```

Note that some of our values did not need anything added to them because the distance between those points was 0. Some points needed to have something _subtracted_ from them because the distance was a negative value. It may be worthwhile to have access to a number line for students working through this so you can demonstrate the concept of positive and negative direction.

**NB:** _This will likely be the end of the first day of this lesson: if that's the case, feel free to include a brief wrap-up to close out student learning. An easy one is to do it a post-it note check-in where students answer one of the following and hand it in as an exit slip:_

1. _What is something you learned today?_
2. _What is something that you still have questions about?_
3. _How can you imagine using this in the future?_

### Creating Our Own Variables (\~10 - 15 min)

**NB:** _This is likely the start of a new day for this lesson block - if so, you an use the first part of students moving several ellipses in a line as a Do Now activity before launching into the lesson._

Ask students to get computers and duplicate the Do Now Starter Code ([p5 editor](https://editor.p5js.org/cs4all/sketches/rJsRRER7Q)). Ask them to move all of the ellipses down thirty pixels. Once students start to finish getting all ellipses shifted down, ask them to move the ellipses back up 40 units. Then ask them to move everything to the right 20 units.

Once students are done, ask them what is frustrating about this process, and what might make it easier.

Students should be able to verbalize that changing every single number individually is frustrating. While most won’t be able to say that making a variable would make this a simpler process, they should be thinking that there must be someway for them to move everything together/at the same time. This is the launch to your activity!

Instead of changing values manually, explain that we can use variables instead. A variable is just a “container” that holds a value which we can then apply and quickly change values in multiple places in our code.

Explain to students that there are three steps to creating a variable:

**Declare** - Declaring our variable is basically just telling the program “hey! I’m creating a variable, and this is what it’s going to be called.” All you need to do when you want to declare a variable is write the term “var variableName”.

**Initialize** - give variableName a value. This is called an assignment operation. We are assigning a value to our variable. If I write variableName = 50, every time I use my variable name, the program will replace it with the number 50.

**Use the variable** - Your code won’t break if you don’t use the variable, but then what was the point? If we add an ellipse at ellipse(100,100,variableName,variableName), our ellipse will be 50px wide and 50px high.

An error proof way for these three steps will be to use three lines of code. See the image below:

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

Notice where we placed these lines of code - the declared variable is way at the top before the `setup` function. We gave it a value in setup (our initialize step), and then used it in our `draw` function, although it could be used in `setup` as well.

This method will work for _all_ data types assigned to variables and is a good practice if you worry your students may become confused. If you have prior coding experience, or have advanced students, you are welcome to talk about other ways to declare and initalize that may be more efficient.

Once students have the idea of using variables, it's time to code one into the program. Begin by telling students you are going to make a variable that will control the y position because we can see that all the ellipses in our design have the _same_ y position. When code repeats, it is usually an indicator that we can make it more efficient.

```javascript
let circleY

function setup(){
    createCanvas(600, 120)
    circleY = 60
}
```

Next, utilize the y variable by plugging it into the code itself:

```javascript
function draw() {
	background(180);
	ellipse(120, circleY, 60, 60);
	ellipse(200, circleY, 60, 60);
	ellipse(280, circleY, 60, 60);
	ellipse(360, circleY, 60, 60);
	ellipse(440, circleY, 60, 60);
}
```

**As you code, discuss the following:**

* Why are we calling our variable `circleY`? Make sure students understand that we name variables useful things so we keep track of them - you might ask them how we could make this even more precise, and then change the variable name to something like ellipseY. You should also model adding comments with your variables about what this will control.
* Where could we use this variable? Students should tell you in the y position.
* What value should this variable have to start? If students aren’t sure, suggest starting at 60 to make sure it runs - then you can change it from there.
* Why do you think we named our variable above all the other functions? This is your introduction to global variables. Some students will see the visual cue that the variable is declared before we use it and that it’s used in two functions - some will not. It’s okay to explain this a bit more, they will see it again in more detail when they learn about random().
* Why did we need to set the value of y in the setup? This is a great question they might not grasp yet, but will during the next lesson - setup runs ONCE and sets up the value of our variable. Draw runs continuously. Right now, nothing will go ‘wrong’ if we give our variable a value in draw, but they it’s good to start getting the differences in now.

After the variable is added in, give it a few different values, running the program each time to see the change (you might want to make the canvas longer for this).

### Designs with One Variable and `random()` (10 - 15 minutes)

