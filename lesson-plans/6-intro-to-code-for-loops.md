---
description: How can we use iteration to abstract artwork?
---

# 6: Intro to Code, For Loops

### Teacher Notes and Overview

This learning activity introduces repetition using for loops. They will change the values inside the for loop to achieve different results in their design. Students will then style their loops as they make designs along the x and y-axis.

Students should be fairly comfortable with loops by the end of this lesson. There will probably still be a lot of syntax errors because students will most likely be experimenting with new ideas so have them use comments and `console.log()` to debug. We highly encourage using pseudo-code in order to help them understand a lot of the concepts taught in this lesson.

This pair programming experience is very open-ended - try to encourage students to talk together about features for their program, rather than each person deciding for the group when it is their turn to navigate.

### Objectives

Students will be able to:

* Explain how the components of the for loops are essential to efficiency&#x20;
* Create for loops&#x20;
* Use for loops to generate multiple shapes Use for loops to increment color change
* Use for loops to generate multiple shapes&#x20;

### Suggested Duration

2-3 Class Periods (\~90 - 135 minutes)

### NYS Standards

**9-12.CT.4** Implement a program using a combination of student-defined and third-party functions to organize the computation.

**9-12.CT.8** Develop a program that effectively uses control structures in order to create a computer program for practical intent, personal expression, or to address a societal issue.

**9-12.DL.1** Type proficiently on a keyboard.

**9-12.DL.2** Communicate and work collaboratively with others using digital tools to support individual learning and contribute to the learning of others.

### Vocabulary

* **Loops** - A sequence of instructions that is repeated until a certain condition is met.&#x20;
* **Iterations** - the repetition of a process or utterance.&#x20;
* **For loop** - loops through a block of code a number of times

### Planning Notes and Materials

There are no specific notes or materials needed for this lesson, but it can help to 'act out' the process of a for loop in real world scenarios, which you may want to plan for.

### Resources

* [Intro to For Loops](https://youtu.be/DszE9QFPGes) (Youtube Video)
* [Styling For Loops](https://youtu.be/9RLDwu0-8hQ) (Youtube Video) | [Starter Code](https://editor.p5js.org/cmorgantywls/sketches/fnbo7fpBH) ([p5 editor](https://editor.p5js.org/cmorgantywls/sketches/fnbo7fpBH) | [repl.it](https://replit.com/@qrtnycs4all/U3LA12-For-Loops-Starter-Code#script.js))
* [Learning Processing: Chapter 6. Loops](http://learningprocessing.com/examples/)
* [Getting Started With p5.js: Chapter 4. Variables (Section: Repetition)](https://p5js.org/books/)

### Assessments

**Formative:**

* Do Now (modifying sketch to include for loop)
* Exercises 1 and 2
* Wrap Up Assignment

**Summative:**

* Upcoming Mini Project
* Upcoming Final Project

### Do Now/Warm Up (\~min - min)

_Ask students:_

Let's say you had a bag of candy and were told _there needs to be one piece **FOR** every student_.

How would they behave/what would they expect to happen?

### Repeat Shapes with a For Loop (\~10 - 15 minutes)

FOR (be careful to specify this is NOT the number) is a control structures that act as a loop. In the instance of our Do Now, this would mean completing the action once of giving a candy for every student present, and then stopping. The looped action is giving candy, and it continues until you are out of candy-less students.

When we think of code, our for loop has three major components:

1. **Initializes a variable** - decide what value to start the loop at. _(If we return to our Do Now example, this would be like saying 'begin with student one on the roster')_
2. **Checks for a condition** - the loop continues until this condition is met. _(In the Do Now, 'all students having one piece of candy' is the condition to stop.)_
3. **Increments the variable** - the way the variable increases with each loop iteration. _(In the Do Now, going from student one on the roster to student two, which would be incrementing by 1.)_

In our code, that looks something like this:

<figure><img src="../.gitbook/assets/Screen Shot 2023-12-06 at 9.52.38 AM.png" alt=""><figcaption><p>Code for a for loop with annotations</p></figcaption></figure>

Once students are familiar with this as an idea, pause to do a brief code along with them to get a row of shapes on the screen. The shape can be anything - here an ellipse is used as an example, but do what makes your students happy.

```javascript
//initialize; check condition; increment variable
for(i = 0; i < width; i += 50){
  ellipse(i, 75, 200)
  console.log(i) //feel free to to add or remove this - it will just show the changing value of i!
}
```

Stress the syntax of the for loop during this code along, specifically the use of semi-colons between each piece of information. Note that 'i' is the classic iterative variable, but it's also important to ensure students understand that like all variables, this could be _anything_ - x, y, rainbowTacos, whatever makes them happy.

Once the code is in, encourage students to explore it in the same way they explored for loops. What if the variable starts at a different value? What if the center condition changes? What if the variable increments differently?

After students have had a chance to explore, explain that they will be completing two challenges before you move on. (This can be done independently, as a pair programming activity, or in small, collaborative groups, as you see fit.) **They will need to write a new for loop for each challenge.** Encourage them to TYPE the loops so they get used to syntax!

* **Challenge 1:** Use a for loop to **draw a column of shapes** that goes up and down the page.&#x20;
* **Challenge 2:** Use a for loop to **draw a line of shapes that goes diagonally** across the page. (HINT: To be diagonal, the x and y values of the shape must both be changing together! Think about math and slope!)

Allow students 7 - 12 minutes to work on these challenges, and then come back together to discuss. Depending on the student's math level, they may need to review diagonally lines, which would simply be a change in both x and y, like so:

```javascript
for(i = 0; i < width; i += 50){
  ellipse(i, i, 200)
}
```

### More Practice (10 - 15 minutes)

If you would like students to have more practice making purposeful for loops, consider asking them to try to recreate one or all of the following:

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

Mild and medium are versions of things students have already created. Spicy can be achieved with the following solution (among others!):

```javascript
x=width //start x on the right side of the canvas

for(y=0;y<=height;y=y+40){
  //draw an ellipse at y location of the variable y
  ellipse(y,y,20,20);
}

for(y=0;y<=height;y=y+40){
  //draw an ellipse at the x and y location of the variable x
  ellipse(x,y,20,20);
  x=x-40//subract 40 from x through each loop}
}
```

### Varying with For Loops - _Intro_ (5 min)

_It is very likely that the above content will take a full class period - feel free to use the introduction of this section as a Do-Now/Warm Up Activity. Alternatively, it can be used to simply allow students to shift their thinking from one task to the next!_

Display the following and ask students to recreate:

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption><p>A row of ellipses increasing in size</p></figcaption></figure>

_In previous lessons, students used for loops to create columns, rows, and diagonal rows. Ideally, we would want students to be using for loops to create a row of 5 circles so if students are still having some confusion with for loops use this opportunity to review loops. Ask any student who was able to create the image above to share out their solution with the class._

### Incrementing Size, Incrementing Color, Specific numbers of repetitions (10 - 15 min)

Students may have taken several paths to recreate the Do Now image; some may have made many ellipses, and some will hopefully still be thinking _for loops_ to make it happen. Regardless of where your class is, make sure that they take some time to code along this example and get everyone on the same page:

```javascript
for(var x = 100; x < width; x = x + 100){
   ellipse(x,60,x/10,x/10);
}
```

The big takeaway here is that **the iterating variable can be used to control more than just position.** This can be, conceptually, quite big for the students; they need to understand that the variable is not _required_ to do any one thing other than hold a number that is slowly incrementing in value, and that number can be used anywhere a number may go in their code. Since we control most everything with numbers, this leaves them with a lot of options!

The second big push for students to get through is that you can do math to - and with - the variable. From where you started, go back to the start, here:

```javascript
for(x=100;x<width;x=x+100){
    ellipse(x,200,x,x)
}
```

This will produce a result like:

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption><p>Overlapping ellipses that increase in size</p></figcaption></figure>

Explain to students that this result is based on the x values getting bigger and controlling the size of the shape, and as we can see, they eventually get so big that the ellipses run off the screen. If the students need an explainer, do a little labeling as you walk through the loop: in the first iteration x is 100, then 200, then 300... all the way until it's massive!

By dividing the x value as we did in the do now, these numbers become more manageable. In the first iteration, instead of 100 the width would be x/10, or 100/10, which would be 10. Then it would be 200/10, which would be 20, so on and so forth until the loop is done running. (If they try to divide by different values, they'll get different results. Play with that together!)

Just to make it abundantly clear, make sure students know that division is just the tip of the iceberg - they can always try multiplying or adding/subtracting to see what results they get, as well! This can be a little nerve-wracking for math fearful students, and it doesn't need to be. Be sure to remind students that it is not at all about them knowing the exact number that is happening as a result of the math they're doing - they just need to be aware of how the operations and values they choose to use will affect the outputs generally. For example, understanding that dividing a whole number by another whole number will result in a smaller value.

There is also no reason to think that this trend of making changes with for loops wouldn't work in other situations. So let's try colors, shall we?

```javascript
for(x=100;x<width;x=x+100){
  fill(0,0,x)
  ellipse(x,100,40,40)
}
```

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption><p>Row of ellipses in subtly different colors of blue</p></figcaption></figure>

Remind students that color values only go up to 255 - so this is a great opportunity to divide the variable by a number so you have a wider range of color shifts! Give students a few minutes to experiment and play. You \*might\* even drop the idea that they try using mouseX or Y as a color value and dividing by an incrementing variable. (It's always a crowd-pleaser.)

### Student Activity: Create Your Own Incrementing Design (10 - 15 min)

Ask students to take what they have learned and try to create their own design by making a unique row of fully styled shapes. They should practice changing size, color, `strokeWeight`, transparency... anything and everything they can think of!

Students looking for an extra challenge may choose to try to style a design they've made previously, like in this example where the mouth of the emoji gets bigger over time:

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption><p>Row of emojis with each mouth getting larger</p></figcaption></figure>

```javascript
function setup() {
  createCanvas(600, 120);
}

function draw() {
  background(220);
	
	for(x=100;x<width;x=x+100){
		//you may want to develop the face here first, then move it into an abstraction!
		weirdFace(x, 60)
	}
	
}

function weirdFace(x, y){
	fill(255,0,0);//red fill
	ellipse(x,y,40,40);//draw an ellipse at that x location
	fill(0);//add a black fill
	ellipse(x+7,y-5,5,10)//draw a smaller ellipse 7 pixels to the right of the face center for right eye
	ellipse(x-7,y-5,5,10)//draw a smaller ellipse 4 pixels to the left of the face center for the left eye
		
	/*the mouth is assigned a height of x/25 so that the height grows through the loop 
	but not as drastically as x alone. 100 is added to x each loop. If it is divided
	by 25, it increments by 4 each loop*/
	ellipse(x,y+10,7,x/25) //draw an ellipse a little bit lower than center
}
```

### {OPTIONAL} Counting in For Loops

This is entirely extra, but you may want to show students more ways to make precise things happen in loops. One way to make sure that, say, the loop always has 5 circles in it is to use a for loop that counts by ones instead of by huge gaps, and then multiplying that value to make the shapes show up as intended. For example:

```javascript
for(i=1; i<=5; i+=1){
  ellipse(i*100,200,50) 
}
```

Would have a similar result to the first for loop they ever saw, the incrementation is just occurring differently. It is _not_ required students know this, but for some, it may be helpful as another approach to looping!

Alternately, if students are uncomfortable with the math, they could create a separate variable that increments inside the loop, making this behave more like a while loop:

```javascript
function setup(){
  createCanvas(400,400);
}
function draw(){
  background(220);
  //create a size variable outside of the loop
  var size= 400
	
  //this loop with repeat five times since the variable was initialized to 0
  ///(initialize the variable; check for a condition; increment the variable)
  for (var i=0; i<5; i+=1){
	//draw ellipses in the center of the canvas set to the size variable
	ellipse(width/2, height/2,size,size)
	//every time the loop runs (which will be 5 times) the size is decreased by 60
	size=size-60
 }
	
}
```

### Wrap-Up (5 min)

Ask students to post their project links in a forum such as Slack or the Google Classroom. Then, have them view and comment on two other projects, leaving a glow and grow for each.

**Guiding questions:**

1. How can we use variables to change multiple parameters?
2. What are some other things we can increment with for loops?

### Extensions and Additions

**1) Nesting For Loops**: Some projects may benefit from knowing how to use one for loop inside of another. (This can also be achieved by having a second variable that increments in the loop, as shown above.) If this is something you're interested in exploring with students, we recommend utilizing[ U3LA1.3: Nested For Loops ](https://cs4all-icm.gitbook.io/js-intro-to-computational-media-2.0/unit-3-arrays-loops-media/u3la1.3-nested-for-loops-for-loops-pt-2)in the Introduction to Computational Media Curriculum.

**2) Advanced students may want to pursue modulos in their program:**

Feel free to reference [this Youtube Video](https://youtu.be/oqJTPyS2rUg) to get started on modulos. Another good introduction is to explain the modulo to students: it looks like a %, is sometimes written as MOD in code, and it does a _very specific thing._ Write a few examples on the board and ask students if they can figure out what's happening. Some examples might look like:

* 4 % 2 = 0
* 5 % 2 = 1
* 10 % 2 = 0
* 13 % 2 = 1

Or:

* 16 % 4 = 0
* 12 % 4 = 0
* 22 % 4 = 2
* 23 % 2 = 1

Try to give them examples where you are modding by several different numbers to avoid students generalizing incorrectly (like saying 'it gives 0 for even numbers and 1 for odd numbers'). The conclusion that students should come to, and the definition you should review together, is a modulo returns the REMAINDER of a division problem. 25 / 5 has no remainder, so 25 % 5 would equal 0. However, 27 / 5 would have a remainder of 2, so 27 % 5 equals 2.

This is a simple overview and mods are a very powerful tool in programming and encryption. A simple way for students to use them is to make things change based on if they are even or odd.
