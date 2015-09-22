#Day 2: Let's Make a Maze!

Today we will be making a maze website with multiple pages, but first let's learn more HTML + CSS to make them look impressive!

###Making Your Own Colors

There is a simple way to do colors in CSS, simply by typing in the color:

```background-color: green;```

But there are many more colors that we don't have names for, like #FF6BC4. That is a hex color - it combines red, blue, and green to make a very specific color. It will give you many many more options for colors to use on your web page.

In order to find the hex value for a specific color, go to [Color Picker](http://colorpicker.com/). Select the color you want and copy the hex value from the top of the screen.

![color picker](https://raw.githubusercontent.com/CoderDojoSV/Medallia-Web-Workshop/master/color%20picker2.png)

If you are interested in learning how the computer knows that #FF6BC4 is that specific shade of pink, ask a mentor! It is really cool!


###Grouping things together with div and span
How can you group a whole bunch of HTML elements together so that you can control them with your CSS or Javascript? 

```html
<div>
   <img src="http://lorempixel.com/150/150/cats/">
   Cat description 1
</div>
<div>
   <img src="http://lorempixel.com/150/150/cats/">
   Cat description 2
</div>
```

Try out both of these - what is the difference?

```html
<span>
   <img src="http://lorempixel.com/150/150/cats/">
   Cat description 1
</span>
<span>
   <img src="http://lorempixel.com/150/150/cats/">
   Cat description 2
</span>
```

Have you noticed how some HTML tags will drop down to a new line while others don't? That is called a block element or an in-line element.

###CSS Select with Class or ID

What if you had two paragraphs of text on your page and you only wanted to give one a green background? You can do that by giving your HTML element a class or ID attribute. You can give you class any name you like (one word only, must start with a letter).

Example: 
```html
<p class="intro">First paragraph of text</p>
<p>Another paragraph of text</p>
```
```css
.intro {
   background-color: green;
}
```

The difference between an ID and a class is that an ID can be used to identify one element, whereas a class can be used to identify more than one.

###Borders with Padding and Margin
Add a div to your page and try out the following CSS:

```css
div {
  background-color: red;
  width: 50px;
  height: 50px;
  border-style: solid;
  border-width: 5px;
  border-radius: 10px;
  padding: 10px;
  margin: 50px;
}
```

How is padding different than margin? How can you use those to arrange items on your page?

Try changing around the different values. Do a search to find the other possible 'border-style' values. 

###Changing the CSS When Your Mouse is Hovering Over It
Add a div to your page and try out the following CSS:

```css
div {
  background-color: red;
}

div:hover {
  background-color: blue;
}
```

###A Fun HTML Tag from the 90s
This tag isn't supposed to be used any more, but it still works in most browsers. Try it!

```html
<marquee>What does this tag do?</marquee>
```

#Let's Make a Maze!
Websites usually have many pages that you navigate by clicking on links. We are going to create your first multiple page website, a link maze with only one way to get to the end.

Go here and click 'remix': https://d157rqmxrxj6ey.cloudfront.net/bskinny129/7892

Notice that all the pages use the same CSS file - this way you can easily control how the whole website looks.

Create your own version! There a lot of different things you can do, so get creative:
* Instead of escaping zombies, come up with your own idea. You can change the words and images.
* Change the CSS to improve how all the pages look.
* Add new HTML files to make the maze longer and more difficult to find the end.

