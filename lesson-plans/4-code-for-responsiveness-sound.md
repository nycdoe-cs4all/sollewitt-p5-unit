---
description: How can user generated sound control program elements?
---

# 4: Code for Responsiveness: Sound

### Teacher Notes and Overview

This is a fairly brief and straightforward lesson - the most fun comes from the play. In p5.js, it's a very quick and easy process to get input from the mic and use that value to control elements of the program. Students generally enjoy using inputs to control their programs, and they'll come up with a lot of creative projects as a result of this lesson!

[This lesson is built on an extension from our Introduction to Computational Media Curriculum.](https://cs4all-icm.gitbook.io/js-intro-to-computational-media-2.0/curriculum-extras/getting-sound-from-mic)

### Objectives

Students will be able to:

* Integrate input from the computer's microphone to their program
* Use volume levels of audio input to control program elements

### Suggested Duration

1 Period (\~45 minutes)

### NYS Standards

**9-12.CT.2** Collect and evaluate data from multiple sources for use in a computational artifact.

**9-12.CT.7** Design or remix a program that utilizes a data structure to maintain changes to related pieces of data.

### Vocabulary

**p5.AudioIn** - a class built into the p5.js sound library that allows the program to connect to your computer's microphone

### Planning Notes and Materials



### Resources

* [Microphone Input ](https://www.youtube.com/watch?v=q2IDNkUws-A)- p5.js Tutorial (Youtube Video)
* [p5.AudioIn](https://p5js.org/reference/#/p5.AudioIn) (p5 Reference Sheet)

### Assessments

**Formative:**

**Summative:**

Upcoming Mini Project

### Do Now/Warm Up (\~3 min)

_Ask students:_

What are some of the different ways we can interact with technology? Think about all the different technologies you use in a day, and all of the different ways that you interact with them.

### Getting Audio in Our Program (\~15 - 20 minutes)

Once students have come up with their list, highlight the option they have to talk to their technology. (Such as saying 'Hey Google' etc.) Today, students are going to get to a point where they can get programs that will start responding to sound from the microphone - to start, they will only be using the volume from the sound, but there is another optional lesson that uses ml5 to classify the sounds they are saying.

Ask students to point their browsers to a new, blank editor. To start, let's just capture the microphone and see what it reports back, like so:

```javascript
let mic

 function setup(){
  createCanvas(400, 400)
  mic = new p5.AudioIn() //gets the incoming audio
  mic.start() //starts reading incoming audio
}

function draw(){
  background(0)
  console.log(mic.getLevel()) //gets the current volume of mic input
}
```

Students have not had to see `console.log()` so far; this function has very little baring on how their program runs, but it IS useful as it will display values in the console. They'll see this more when they learn about conditionals!

When students run this example, they should first see this (exactly, if they're in Chrome, or as some similar pop up in another browser):

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption><p>Pop up notification asking user to allow or block the microphone use.</p></figcaption></figure>

We want to hit 'Allow' so that our browser can get data from our microphone. Stress to students that this is acceptable as we know what this website is doing with our microphone data - since we are writing the code that will use it - but they should be cautious about just hitting allow on any website they are confronted with.

Once students have hit allow, they should see a bunch of numbers being printed to the console. Have students practice talking/snapping/clapping near their computer's microphone to watch how this value changed. Ask students to all be as quiet as possible to see what the lowest number they can get is, and then as loud as possible (within reason - you know how thin your walls are!) to see what the highest number they can get is. They should notice that they are always getting numbers between 0 and 1, and most likely those values are between 0.01 and 1.

So, what if they wanted to use this value? They could just try saving it to a variable and plugging it directly into a part of their program, like here where it controls the size of an ellipse:

```javascript
let mic

 function setup(){
  createCanvas(400, 400)
  mic = new p5.AudioIn() //gets the incoming audio
  mic.start() //starts reading incoming audio
}

function draw(){
  background(0);
  let circSize = mic.getLevel()
  
  ellipse(200, 200, circSize)
}
```

They should notice that their circle is very, VERY, speck-of-dust-style small. That's because this number is incredibly miniscule - we need a way to make it bigger! One option that we can use to scale values is to multiply them by a larger number, as seen here:

```javascript
let mic

 function setup(){
  createCanvas(400, 400)
  mic = new p5.AudioIn() //gets the incoming audio
  mic.start() //starts reading incoming audio
}

function draw(){
  background(0)
  let circSize = mic.getLevel()
  
  ellipse(200, 200, circSize*200)
}
```

This is a completely acceptable solution, but it doesn't give us the most control. Now, our circle will always be somewhere between 0 and 200 pixels in size, based on the little expression we have set up to calculate size. But what if we want the circle to always be between 100 and 200? Or 200 and 400?

To do that, we need to use the map function. The map function, which is brand new to us takes a changing variable, it's original range (in this case, 0 to 1), and a new range. It then 'maps' the original range to the new range so that all the values proportionally line up. In this example, we might say:

```javascript
let mic

 function setup(){
  createCanvas(400, 400)
  mic = new p5.AudioIn() //gets the incoming audio
  mic.start() //starts reading incoming audio
}

function draw(){
  background(0)
  let circSize = map(mic.getLevel(), 0, 1, 100, 350)
  
  ellipse(200, 200, circSize)
}
```

Now, when the volume is 0, the circSize will be set to 100. When the volume is as loud as possible - 1 - it will be 350. If the volume is somewhere in between, the mic level will be proportionally matched to a value between 100 and 350. Allow students time to test by talking/clapping/snapping near the microphone again. Then, adjust the 'new range' values (currently 100 and 350) in the map function to see how this might change.

### Create Something Sound Reactive (\~15 - 20 minutes)

Ask students to create a brief design using the skills they've learned so far.

They will be trying to use microphone input to make several elements of their program reactive to the volume coming in from the microphone. By using the map function, or multiplying the .getLevel() value by different numbers, they should be able to make multiple elements react a little differently.

### Wrap Up (\~5 minutes)

Structured shares:

Ask students to share their project on the board and explain how it works and one challenge they had. At the start of their share, have the class make a variety of levels of noise to get the project to react appropriately.

### Extension and Additions

While it is not a part of this curriculum, a logical next step is to pull in machine learning to make the program reactive to _certain words._ [You can find instructions to do that in the original Introduction to Computational Media curriculum](https://cs4all-icm.gitbook.io/js-intro-to-computational-media-2.0/curriculum-extras/sound-recognition-with-ml5). This is _entirely optional_ and will take an additional 1-2 periods to tackle, should you choose to take that route.
