#Day 3: Beginning with Javascript

Today we will be starting with Javascript - the way you can make your websites interactive!

You have been amazingly creative with your stories, and today we will learn how to make them interactive with Javascript

Javascript is the computer language that runs in web browsers (and increasingly, everywhere else, too).
Javascript has good parts and bad parts.  The bad parts make it very hard to build large web sites, but some times make it easier to do small things.  

###Start by showing prompts and alerts

You can run javascript right on the address bar of your browser.  Just paste this line (tip: Control-L or Command-L takes you there without touching the mouse) and type the following line:

```javascript
javascript:alert("Hello World");
```

Did you see a box pop up?

Prompts are a lot like alerts, but you can ask a question and record the answer in a "variable".  A variable is how a program remembers something.  The program code sets the variable.  Let's use a variable to store a name.  (The name is a bunch of characters, usually called a String.  Variables are often numbers.  There are more complex variable tyles we will talk about in a moment.)

Make a new project and change the body to this:
```html
<body>

  <h1 id="welcome">Welcome to Thimble</h1>

  <p>Make something <strong>amazing</strong> with the web!</p>
  <script>
    var name = prompt("What is your name?");
    console.log("Hello "+name);
    document.getElementById("welcome").innerHTML = "Welcome to Thimble, "+name;
  </script>
</body>
```

The name is shown in two different places.  You hopefully saw the name appear in the welcome message.  We used a *function*  called getElementById to hunt down the welcome message in the web page (also called the *document*) and change it.  Cool, huh.  (Notice that the html had to name the welcome element by id="welcome".  In earlier weeks we might have given it an id to apply a style.

The other place you would see the name is on the console log.  Open up the console log by the developer tools.  On Chrome, on a PC, press Control-Shift-I and on a Mac, press Command-Option-I.  In the top of the area that appears, clock on the word "Console".  In this window, you will see output that Javascript produces, either console logs as they are written, or warnings and errors in the page itself.

### how to handle a click event to run code

Another important type of variable is the Array.  An array is a list of things, often strings.



###discuss variables, discuss functions

###Make a quiz game
