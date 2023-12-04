# 5: Code for Interactivity: Conditionals

### Teacher Notes and Overview

* Utilize ICM resources - _abbreviate and link extra resources for interested parties._
* Make things change based on mouse position

### Objectives

Students will be able to:

* Understand conditional logic within real-world and programmatic examples
* Code conditionals to change appearance of objects on canvas

### Suggested Duration

1-2 Periods

### NYS Standards

\[COMING SOON]

### Vocabulary

* **Conditional statements** - is a set of rules performed if a certain condition is met&#x20;
* **Boolean expressions** - is a logical statement that is either TRUE or FALSE

### Planning Notes and Materials



### Resources



### Assessments

**Formative:**

**Summative:**

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

* 26>5 → 26 is greater than 5. Let's read that as a question. Is 26 greater than 5? Yes it is. This expression evaluates to "true."
  * If we wanted to test this in our editor, we could enter `console.log(26>5)` at the top of our program. Hit play, and we should see 'true' in the console!
* 10=14 → Since 10 is not equal to 14. This expression evaluates to "false"&#x20;
  * Try entering `console.log(10==14)` in a program. You should get 'false' in the console!
* 4>210 → This expression is also "false"&#x20;
  * Try entering `console.log(4>210)` in a program. You should get 'false' in the console!
* 2=2 → "true"
  * Try entering `console.log(2==2)` in a program. You should get 'true' in the console!

These "greater than" or "less than" signs are relational operators - they compare two numbers, which is what we're going to do in our first conditional statement.

The boolean expression inside the parentheses is the expression being evaluated. If the expression is true, then the computer will execute the code inside the curly brackets. If it evaluates to false, the code is not run and the program will continue with the code that follows the expression.

```javascript
if(5<6){
    background(0)
} //background will turn black since 5 IS less than 6.

if(5<4){
    background(0)
} //background will not be black because 5 IS NOT less than 4. Code will be skipped!
```

