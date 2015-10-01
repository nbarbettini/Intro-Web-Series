#Day 3: Beginning with JavaScript

You have been amazingly creative with your pages and stories, and today we will learn how to make them even more interactive with JavaScript!

Covering JavaScript in one night is ambitious.  The goal is to get to the point where you understand what happens on this page:  https://d157rqmxrxj6ey.cloudfront.net/jamwave/18168  There's *a lot* of information here, so if you feel fatigued, feel free to jump to the end and explore Khan Academy's Hour of Code for JavaScript.  It is really good and isn't just on one long page.

Tonight, we'll go over
- Introducing JavaScript: 
  * What JavaScript looks like (very quickly)
  * Simple alerts, prompts, and variables
  * Simple if..then..else control
  * a bit of debugging advice
  * Putting JavaScript in a different file
- Then for *your* project
  * How to define a list of colors
  * Use a function to change color of the text. 
  * (optional) How to make a button and make it do something
- We'll wrap up with suggestions on where you can learn more on your own
 
 
JavaScript is the computer language that runs in web browsers (and increasingly, everywhere else).
JavaScript has good parts and bad parts.  The bad parts can make it challenging to build large web sites, but some times make it easier to do small things, particularly when learning.  So, not everything you see here is how professionals use JavaScript.  

### What JavaScript looks like (the syntax)

There's so much to say about syntax that it could take all night, but we know you want to get to the fun stuff, so glance over this and keep moving on.  You will see this syntax used in the examples that follow this section.

Some of the key JavaScript syntax concepts are 
- Statements should end in semicolons: ```;```
- Usually, statements are written one-per-line  (unlike HTML)
- Typically, JavaScript is run in functions, which have names, accept parameters, and "do something specific".  You call functions by stating their name and putting ```()``` behind the name, and including any parameters between the parenthesis.
- You must use ```{``` paired with ```}``` when you have more than one line of code grouped together, and sometimes (like a function's code) matching ```{``` paired with ```}``` is required.
- JavaScript has control mechanisms like if..then..else , loops (see below), and function calls.  Here's what an if..then..else statement with a pretend function call looks like...
```javascript 
if (something-is-true) {
  doThis();
} else {
  doThat();
}
```
- when you are writing code inside a control structure, be sure to indent it at least 2 spaces more than the lines above, and make a habit of using curly braces around blocks of code.  

#Showing alerts and prompts

You can run JavaScript right on the address bar of your browser.  (Make a new tab, then...) type the following line:

```javascript
javascript:alert("Hello World");
```

Did you see a box pop up?


Prompts are a lot like alerts, but you can ask a question and save the answer in a "variable".  A variable is how a program remembers something.  Variables have names (and the names cannot contain anything other than letters, numbers, and the underscore character.)  When you first use a variable, you have to declaare it is a variable by the magic letters **var** in front of it.  The program code stores the variable's value.  Let's use a variable to store a name.  (The value is a bunch of characters, usually called a String.  Variables can store strings, numbers, and many more complex variable types.   We will talk about another, called an array, a bit later.)

Make a new project and change the body to this:
```html
<!DOCTYPE html>
<html><body>

  <h1 id="welcome">Welcome to Thimble</h1>

  <p>Make something <strong>amazing</strong> with the web!</p>
  <script>
    var name = prompt("What is your name?");
    alert("Hello "+name);
  </script>
</body></html>
```

By the way, we put some javascript right in the html page.  We will not do this for long--it belongs in a separate file.  

You probably noticed that the name was shown in an alert box.  That gets irritating.  Delete that alert line and replace it with this.  It should be placed right before the final ```</script>``` tag: 
```javascript
    document.getElementById("welcome").innerHTML = "Welcome to Thimble, "+name;
```
Now, you hopefully saw the name appear at the end of the welcome message.  We used a **function** called `getElementById` to hunt down the welcome message in the web page (also called the **document**) and change it.  Cool, huh?  (Notice that the html had to name the welcome element by ```id="welcome"```.  In earlier weeks we might have given it an id or class to use css to apply a style.  Later tonight, we'll use javascript to apply a new style.


## Loops, If statements, and tests

JavaScript is like most computer languages because it has ways to control the program action.  Two basic control mechanisms are loops and conditionals.  ```If (conditional_expression)``` lets you test and choose if a block of code should be run before running it.  Similarly, you typically use a conditional_expression to know when to stop the loop.

Let's modify the web page just a bit more to create a place where output can appear.
Put this line before the `<script>` tag you put in earlier.

```html
<p id="output">How happy am I?</p>
```

Now, after the opening ```<script>``` tag but before the closing ```</script>``` tag, add the following
```javascript
var i=0;
while (i<10) {
   document.getElementById("output").innerHTML += " :)";
   i += 1;
}
```

We set the value of ```i``` first to 0, then added a smiley and incremented ```i``` until it was no longer less than 10.
So, how many smileys were printed?

Note: += is a math-like operator that says 'add the thing on the right to the existing thing on the left of +='.
So if i was 0, then i += 1 will increment i to be 1.  Since we're adding the smiley face to the innerHTML, it will just add another smiley the end.

People who create programming languages usually try to make ways to write stuff shorter, so the following line is actually identical.

```javascript
for (var i=0; i < 10; i+=1) {
  document.getElementById("output").innerHTML += ":) ";
}
```

Warning: adding strings to existing strings gets slower the more times it happens.  If you changed the numer of times it loops from 10 to a higher number like 100, you would see it much, much slower the higher you went.  

## Advice: When you don't know what is going wrong...
This is important advice if what you are doing is not working and you don't know why!
If something is wrong with your JavaScript, the JavaScript Console may be the only place to see error messages.  Open up the console log by the developer tools.  On Chrome, on a PC, press Control-Shift-I and on a Mac, press Command-Option-I.  In the top of the area that appears, click on the word "Console".  In this window, you will see output that JavaScript produces, either console logs as they are written, or warnings and errors in the page itself.  (On Firefox, use Control-Shift-K or Command-Option-K.  Internet Explorer? F12) 
Tip: You can put messages you write in the console log, too.  For instance, after you asked for name, you could also print it in the console.
```javascript
console.log("Someone named "+name+ " is visiting the page");
```
Of course, you also created the output area, and you can write to that and see it in the browser itself.


Note: So, now I'm going to stop doing two bad things.  First, it's time to stop putting JavaScript in the HTML page!
Second, I will stop appending to a string inside a loop.

## Using a separate JavaScript file
If you are using Mozilla Thimble, in the upper left corner, click the green + , which is the way to say 'add a new file', then choose JavaScript.  (If you hid the file tray by clicking the left-pointing arrow previously, then click the right-pointing arrow to restore it.)  You will see a new file created, probably called script-1.js  
The first bunch of writing is called a comment.  It is the way you can leave notes to yourself or others.  At the time this was written, it looks like this:

```javascript
/***************************
This is JavaScript (JS), the programming lanaguage that powers the web (and this is a comment, which you can delete).

To use this file, link it to your markup by placing a <script> in the <body> of your HTML file:

  <body>
    <script src="script.js"></script>
...    
```

It's important to get the ```<script...``` tag line and copy it into your html file.  Note that the comment acts like the file is called script.js, so after you copy the line in your html file, make sure you get the name to match, probably by adding '-1' .  (If you prefer, it's prettier to rename the new file's name.)  Also, For now, I recommend that it be the last line before the closing body tag.


Now, you can take the javascript code that asked for a name and copy it into this new .js file.
```javascript

function greetMe(name) {
  var today = new Date();
  alert("Hello " + name + ", today is " + today.toDateString());
}

var name = prompt("What is your name?");
greetMe(name);
```

Then, go back and replace the old script block with this
```html
    <script src="script-1.js"></script>
</body>
```

The code that was put into the file you created uses a **function** to do it's work.
You were able to use it just by passing in the name you gathered earlier.
Function code is only run when some other code calls it, but it is good practice to make sure it has been seen by the browser prior to being called, otherwise the browser will not know what to do when it sees it.  (If you called greetMe before declaring what greetMe should do, you would see an error in the javascript console.)

The examples so far are visible at https://d157rqmxrxj6ey.cloudfront.net/jamwave/15578
# Your Project

We have been excited to see how you have built projects based on your interests, and we want to encourage you to continue doing that.
So, we want to give you a few JavaScript tricks that can make your page even more interactive (or more automated).
Remember, you need to include your JavaScript file in the HTML.
```html...
    <script src="script-1.js"></script>
<body>
```

## Create an array of colors
An important type of variable is the Array.  An array is a list of things, and you can get to the items one-by-one.  This is an example array of strings that happen to be color names:  

```javascript
var colors = ['red', 'green', 'blue', 'orange', 'yellow'];
```

You can learn the length of an array by the .length property.  (It's a property, not a function, so you do not use ```()``` to get the value.)

You can try this if you want to see it in action

```javascript
var colors = ['red', 'green', 'blue', 'orange', 'yellow'];
alert("I know of "+colors.length+" colors");
colors.push('brown','cyan','navy','olive');
alert("Now I know of "+colors.length+" colors");
```

## Introducing Math.random()

JavaScript has many math functions that can work with numbers.  (Numbers can be integers or floating point numbers and unlike nearly all other computer languages, you don't have to treat them differently.)

If you are wanting to do something fun to a web page, adding randomness by the ```Math.random``` function.
Calling Math.random returns a random number between 0 and 1.  You need to multiply it by the array length, and then turn it into an integer in order to use it to get a value from an array.  Math.floor takes a floating point number and drops the fraction portion (For example, Math.floor(1.99) returns 1.

```javascript
var colors = ['red', 'green', 'blue', 'orange', 'yellow'];
var colorIndex = Math.floor(Math.random() * colors.length);
document.getElementById("welcome").style.color = colors[colorIndex];
```


## Use a loop to change color
Another javascript control is the while statment.  We've used it already, but lets use it to change the color of the welcome message.  (Remember that your HTML needs to declare that one area of text is ```id="welcome"```
Try this
```javascript
/* use your color array from earlier!! var colors = ['red', 'green', 'blue', 'orange', 'yellow']; */
var colorsCycleCounter = 0;
function cycleColor() {
  while (colorsCycleCounter < colors.length) {
    document.getElementById("welcome").style.color = colors[colorsCycleCounter] ;
    colorsCycleCounter += 1;
  }
  sleep(100);
}
cycleColor();
```

## Introducing setInterval

One of the fun things you can do is to make something happen automatically.  JavaScript's ```setInterval()``` is a way to make something happen again and again over time.  It is tricky to get right (because of variable scope), and it is very easy to bog down a computer to the point where it is unusably slow (if many fast interval timers are running or they have lots of code) but can do some cool effects if used correctly.

Try this change to cycleColor and how it is wired into an interval timer
```javascript
/* use your color array from earlier!! var colors = ['red', 'green', 'blue', 'orange', 'yellow']; */
var colorsCycleCounter = 0;
function cycleColor() {
  document.getElementById("welcome").style.color = colors[colorsCycleCounter] ;
  if (colorsCycleCounter >= colors.length) {
    colorsCycleCounter=0;
  } else {
    colorsCycleCounter += 1;
  }
}
var colorCycleIntervalTimer = setInterval(cycleColor,100); /* trigger every 0.1 seconds*/
```

One thing that this code neglects is to clean up the timer.  Let's say you only want the color to cycle for a little while, then stop, this would be better code...
```javascript
var colorsCycleCounter = 0;
function cycleColor() {
  document.getElementById("welcome").style.color = colors[colorsCycleCounter % colors.length] ;
  if (colorsCycleCounter <100) {
    colorsCycleCounter += 1;
  } else {
    clearInterval(colorCycleIntervalTimer);
  }
}
var colorCycleIntervalTimer = setInterval(cycleColor,100);
```

You can see this in action at https://d157rqmxrxj6ey.cloudfront.net/jamwave/18168

*If you are getting tired of reading this page, skip to the end and try Khan Academy's Hour of Code on JavaScript.*

## (Optional) Make a button

Buttons are actually created with HTML.  The oldest use of a button is for telling a web page's form that you are done filling it in and that the input should be sent to a web server.  That's not the only use for a button,  but it's the default use, so code has to be written if you don't want information to be sent to a web server and new page to be displayed.  In particular, you can run javascript when a button is pressed, and the button can do something to the web page you are looking at.

In your javscript file, add a bit of code to clear your output area.  We will put it in a function that can be called when the button is clicked.  Try this:
```javascript
function clearOutput() {
  document.getElementById("output").innerHTML = "";
}
```

Then add the button and its callback function to the HTML
```html
<button id="myButton" type="button" onClick="clearOutput();return false;">Clear It!</button>
```
Expert Tip: the ```return false;``` prevents the page from going away and a request being sent to the web server.

## Buttons to make images bigger or smaller.

Buttons are also frequently used to do things with images, like make slide shows go to the next image, or make maps get bigger or smaller.  Let's mix it up and add button to make the images you used last week get bigger or smaller.

Last week, I added this image to the presentation

Logo: 
![alt text](https://rawgithub.com/CoderDojoSV/Intro-Web-Series/master/Day%202/HTML5_and_CSS3_badges.svg "logo")

Let's tweak the HTML to give images a slightly better class name.

```html
<img class="centeredImage" width="600px" src="https://rawgithub.com/CoderDojoSV/Intro-Web-Series/master/Day%202/HTML5_and_CSS3_badges.svg">
```

and the css
```css
img.centeredImage {
    display: block;
    margin-left: auto;
    margin-right: auto;
}
```

Next, let's write a bit of JavaScript and HTML to add sizing buttons.

```html
<p>
<button id="smallerButton" type="button" onClick="javascript:scaleImages(0.9);return false;">Smaller</button>
<button id="biggerButton" type="button" onClick="javascript:scaleImages(1.1);return false;">Bigger</button>
</p>
```

Now, if you had one or more images with the class centeredImage, you can make them all bigger by this code. 
Note I am using a global variable (which is not good) and that there are 
```javascript
var currentWidth=100;
function scaleImages(scale) {
  currentWidth *= scale;

  var elems = document.getElementsByClassName("centeredImage");
  for (var i = 0; i < elems.length; i++) {
    elems[i].style.maxWidth = currentWidth + '%';
  }
}
```

This is a little different than the function you saw before.  Rather than asking for one element that matches a single id, we're asking for all elements that match a class.
And, rather than iterating one-by-one with an index (i), we are asking javascript to iterate through all of them.

You can see an example of this code at https://d157rqmxrxj6ey.cloudfront.net/jamwave/17762




# Project suggestions

- Can you apply a random background color chosen from a list?  You would want the list to be lighter colors (see http://www.w3.org/TR/css3-color/#svg-color) or choose your own from a color picker (inside Thimble or https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Colors/Color_picker_tool or http://colorpicker.com)  OR if you use dark colors, use CSS to change your default color to be very light.
- Can you put together everything you learned to use an array of URLs to randomly choose the image that is loaded as you go from page to page in your site?
- Can you use a timer to make the page automatically choose where to go next (after, say, 10000 milliseconds?)  Setting ```location.href=``` will cause the browser to go to the location you set.

# Next Steps

We barely scratched the surface of JavaScript in this class.  You can easily learn more online...

## Khan Academy's Hour of Code with JavaScript
If you run out of ideas tonight and.or just want a quick lesson that takes about an hour, look at Khan Academy's Hour Of Code lesson at https://www.khanacademy.org/computing/hour-of-code

## still more...
There is a wealth of resources for learning JavaScript.  
Khan Academy's site is truely an awesome way to learn JavaScript.  https://www.khanacademy.org/computing/computer-programming/programming

The reason we chose Thimble for this class is that it is structured for learners.  Scroll on down at https://thimble.mozilla.org/ and you will see many projects.  Choose one that looks interesting.

If you visit the official Hour Of Code site at https://code.org/learn , you will see recommendations for several great, free sites for learning javascript.  There are a number of very good paid sites as well.
