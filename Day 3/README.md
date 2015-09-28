#Day 3: Beginning with Javascript

Today we will be starting with Javascript - the way you can make your websites interactive!

You have been amazingly creative with your stories, and today we will learn how to make them interactive with Javascript

Javascript is the computer language that runs in web browsers (and increasingly, everywhere else, too).
Javascript has good parts and bad parts.  The bad parts make it very hard to build large web sites, but some times make it easier to do small things.  

#Showing prompts and alerts

You can run javascript right on the address bar of your browser.  Just paste this line (tip: Control-L or Command-L takes you there without touching the mouse) and type the following line:

```javascript
javascript:alert("Hello World");
```

Did you see a box pop up?


Prompts are a lot like alerts, but you can ask a question and record the answer in a "variable".  A variable is how a program remembers something.  The program code sets the variable.  Let's use a variable to store a name.  (The value is a bunch of characters, usually called a String.  Variables are often numbers.  There are more complex variable types we will talk about in a moment.)

Make a new project and change the body to this:
```html
<body>

  <h1 id="welcome">Welcome to Thimble</h1>

  <p>Make something <strong>amazing</strong> with the web!</p>
  <script>
    var name = prompt("What is your name?");
    alert("Hello "+name);
    document.getElementById("welcome").innerHTML = "Welcome to Thimble, "+name;
  </script>
</body>
```

We put some javascript right on the web page.  We will not do this for long.  You notice that the entered name is shown in an alert box.  

Now add the next line before the final </script> tag.
```html
    document.getElementById("welcome").innerHTML = "Welcome to Thimble, "+name;
```
Now, you hopefully saw the name appear in the welcome message.  We used a **function** called `getElementById` to hunt down the welcome message in the web page (also called the **document**) and change it.  Cool, huh.  (Notice that the html had to name the welcome element by id="welcome".  In earlier weeks we might have given it an id to apply a style.

## Loops

Javascript is like most computer languages because it has ways to control the program action.  Two basic control mechanisms are loops and conditionals.  You usually use a conditional to know when to stop the loop.

Let's modify the web page just a bit more to create a place where output can appear.
Put this line before the `<script>` tag you put in earlier.

```html
<p id="output">How happy am I?</p>
```

Now, before the final script line, add the following
```javascript
var i=0;
while (i<10) {
   document.getElementById("output").innerHTML += ":) ";
   i += 1;
}
```

We set the value of i first to 0, then added a smiley and incremented i until i was no longer less than 10.
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
If something is wrong with your javascript, the Javascript Console may be the only place to see it.  Open up the console log by the developer tools.  On Chrome, on a PC, press Control-Shift-I and on a Mac, press Command-Option-I.  In the top of the area that appears, click on the word "Console".  In this window, you will see output that Javascript produces, either console logs as they are written, or warnings and errors in the page itself.  (On Firefox, use Control-Shift-K or Command-Option-K.  Internet Explorer? F12) 
Tip: You can put messages you write in the console log, too.  For instance, after you asked for name, you could also print it in the console.
console.log("Someone named "+name+ " is visiting the page");
Of course, you also created the output area, and you can write to that and see it in the browser itself.


Note: So, now I'm going to stop doing two bad things.  First, it's time to stop putting javascript in the html page!
Second, I will stop appending to a string inside a loop.

## Using a separate JavaScript file
If you are using Mozilla Thimble, in the upper left corner, click the green + that means 'add a new file', then choose Javascript.  (If you hid the file tray by clicking the left-pointing arrow previously, then click the right-pointing arrow to restore it.)  You will see a new file created, probably called script-1.js  
The first bunch of writing is called a comment.  It is the way you can leave notes to yourself or others.  At the time this was written, it looks like this:

```javascript
/***************************
This is JavaScript (JS), the programming lanaguage that powers the web (and this is a comment, which you can delete).

To use this file, link it to your markup by placing a <script> in the <body> of your HTML file:

  <body>
    <script src="script.js"></script>
...    
```

If you thought about deleting the comment, as it suggests in the comments, it's pretty important to get the script tag line and copy it into your html file.  Note that the comment acts like the file is called script.js, so after you copy the line in your html file, make sure yu get the name to match, probably by adding '-1' .  Also, For now, I recommend that it be the last line before the closing body tag.

```html
...
    <script src="script-1.js"></script>
</body>
```

Now, you can take the code that asked for a name and integrate it with the code that is put into this file.
```javascript

function greetMe(name) {
  var today = new Date();
  alert("Hello " + name + ", today is " + today.toDateString());
}

var name = prompt("What is your name?");
greetMe(name);
```

The code that was put into the file you created uses a *function* to do it's work.
You were able to use it just by passing in the name you gathered earlier.
Function code is only run when some other code calls it, but it is good practice to make sure it has been seen by the browser prior to being called, otherwise the browser will not know what to do when it sees it.  (If you called greetMe before declaring what greetMe should do, you would see an error in the javascript console.

# Your Project

We have been excited to see how you have built projects based on your interests, and we want to encourage you to continue doing that.
So, we want to give you a few javascript tricks that can make your page even more interactive (or more automated).
Remember, you need to include your javascript file in the html.
```html
    <script src="script-1.js"></script>
<body>
```
## Make a button

HTML is used to actually create a button.  Usually a button is used to be the thing you press after you fill in a form, and will then send the information to the web server.  But that's not the only use for a button.  You can run javascript when a button is pressed, and it does not have to send data to a server.

In your javscript file, add a bit of code that can clear your output area.  We will put it in a function that can be called when the button is clicked.  Try this:
```javascript
function clearOutputDev() {
  document.getElementById("output").innerHTML = "";
}
```

Then add the button and its callbackto the HTML
```html
<button id="myButton" type="button" onClick="clearOutputDiv();return false;">Click Me!</button>
```

## Buttons to make images bigger or smaller.

Buttons are also frequently used to do things with images, like make slide shows go to the next image, or make maps get bigger or smaller.  Let's mix it up and add button to make the images you used last week get bigger or smaller.

Last week, I added this image to the presentation
[logo]: https://raw.githubusercontent.com/CoderDojoSV/Medallia-Web-Workshop/master/HTML5_and_CSS3_badges.svg "logo"

Let's tweak the HTML to give images a slightly better class name.

```html
<img class="centeredImage" width="600px" src="HTML5_and_CSS3_badges.svg">
```

and the css
```css
img.centeredImage {
    display: block;
    margin-left: auto;
    margin-right: auto;
}
```

Next, lets write a bit of javascript and html to add sizing buttons.

```html
<button id="smallerButton" type="button" onClick="scaleImages(0.9);return false;">Smaller</button>
<button id="biggerButton" type="button" onClick="scaleImages(1.1);return false;">Bigger</button>
```

Now, if you had one or more images with the class centeredImage, you can make them all bigger by 
```javascript
function scaleImages(scaleFactor) {
  for (var oneImage in document.getElementsByClassname("centeredImage") {
     oneImage.width *= scaleFactor;
  }
}
```

This changes what you've seen by a bit.  Rather than asking for one Id, we're asking for all that match a class.
And, rather than iterating one-by-one with an index (i), we are asking javascript to iterate through all of them.

## create an array of colors
Another important type of variable is the Array.  An array is a list of things, often strings.

## Use a loop to change color

## introduce a Math.random.

## introduce setInterval.

The other place you would see the name is on the console log.  Open up the console log by the developer tools.  On Chrome, on a PC, press Control-Shift-I and on a Mac, press Command-Option-I.  In the top of the area that appears, clock on the word "Console".  In this window, you will see output that Javascript produces, either console logs as they are written, or warnings and errors in the page itself.

# bigger examples
?magic 8 ball?  
?number guessing game?
