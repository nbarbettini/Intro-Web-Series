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
   document.getElementById("welcome").innerHTML += ":) ";
   i += 1;
}
```

Note: += is a math-like operator that says 'add the thing on the right to the existing thing on the left of +='.
So if i was 0, then i+= 1 will change i to be i.  If it was a string, it will just ad it to the end.

People who create programming languages usually try to make ways to write stuff shorter, so the following line is actually identical.

```javascript
for (var i=0; i < 10; i+=1) {
  document.getElementById("welcome").innerHTML += ":) ";
}
```

Another note: adding strings to existing strings gets slower the more times it happens.  If you cn=hanged the max from 10 to 100, you would see it gets much slower.  

Note: So, now I'm going to stop doing two bad things.  Next time, I will avoid adding strings, and it's time to stop putting javascript in the html page!



# Your Project

Move to a separate js  (needs this)

```html<body>
    <script src="script.js"></script>
```

##click image to get bigger

## create an array of colors
Another important type of variable is the Array.  An array is a list of things, often strings.

## Use a loop to change color

## introduce a Math.random.

## introduce setInterval.

The other place you would see the name is on the console log.  Open up the console log by the developer tools.  On Chrome, on a PC, press Control-Shift-I and on a Mac, press Command-Option-I.  In the top of the area that appears, clock on the word "Console".  In this window, you will see output that Javascript produces, either console logs as they are written, or warnings and errors in the page itself.

# bigger examples
?magic 8 ball?  
?number guessing game?
