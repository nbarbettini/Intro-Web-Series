#Day 2: More HTML and CSS

Today we will be making a maze website with multiple pages and learning more HTML + CSS to make them look impressive!


###Making Your Own Colors

There is a simple way to do colors in CSS, simply by typing in the color:

```background-color: green;```

But there are many more colors that we don't have names for. As we saw in the earlier example, it used a color #FF6BC4. That is a hex color - it combines red, blue, and green to make a very specific color. It will give you many many more options for colors to use on your web page.

In order to find the hex value for a specific color, go to [Color Picker](http://colorpicker.com/). Select the color you want and copy the hex value from the top of the screen.

![color picker](https://raw.githubusercontent.com/CoderDojoSV/Medallia-Web-Workshop/master/color%20picker2.png)

If you are interested in learning how the computer knows that #FF6BC4 is that specific shade of pink, ask a mentor! It is really cool!



###FUN HTML TAG FROM THE 90s: marquee
This tag isn't supposed to be used any more, but it still works in most browsers. Try it!

```html
<marquee>What does this tag do?</marquee>
```

###Grouping things together with div and span
How can you group a whole bunch of HTML elements together so that you can control them with your CSS or Javascript. 

```html
<div>
   <img src="http://lorempixel.com/150/150/cats/">
   The caption for the image
</div>   
```

Try out both of these - what is the difference?

```html
<span>
   <img src="http://lorempixel.com/150/150/cats/">
   The caption for the image
</span>   
```

Have you noticed how some HTML tags will drop down to a new line while others don't? That is called a block element or an in-line element. 

###CSS Select with class or ID

What if you had two paragraphs of text on your page and you only wanted to give one a green background? You can do that by giving your HTML element a class or ID.

Example: 
```html
<p>First paragraph of text</p>
<p>Another paragraph of text</p>
```


###What other CSS things do we wnat to do?
Show border, padding, margin
Show onhover


###MAKE A MAZE!
This will require downloading a text editor, posting on neocities.org

Should we give a starter project / example? 

Show how to link a CSS file that is shared by all HTML pages on the site
