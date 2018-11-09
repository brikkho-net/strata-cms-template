---
date: 2018-11-22T20:04:40.407Z
title: Using Conditional Rendering and displaying lists in ReactJS
---

When using conditional rendering, it is important to first create a list using an object and then output that object in the render section.  We can use the map function to iterate through the array of objects to add data to the variable.

Given the code below, we use the map() function to take an array of numbers and add it to an unordered list with their values. We assign the new array returned by map()
<p data-height="265" data-theme-id="0" data-slug-hash="GjPyQr" data-default-tab="js,result" data-user="gaearon" data-pen-title="List of Numbers" class="codepen">See the Pen <a href="https://codepen.io/gaearon/pen/GjPyQr/">List of Numbers</a> by Dan Abramov (<a href="https://codepen.io/gaearon">@gaearon</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>
<iframe width="100%" height="475" src="https://stackblitz.com/edit/react-rqdprk?embed=1&file=index.js" frameborder="0"></iframe> 

1. Create an input field (in App component) with a change listener which outputs the length of the entered text below it (e.g in a paragraph)
2. Create a new component (=> ValidationComponent) which receives the text length as a prop.
 
3. Inside the ValidationComponent, either output "Text too short" or "Text long enough" depending on the text length (e.g take 5 as a minimum length)
<iframe width="100%" height="475" src="https://stackblitz.com/edit/react-rqdprk?embed=1&file=Components/Validation.js" frameborder="0"></iframe>
4. Create another component (=> CharComponent) and style an inline box (=> display: inline-block; padding: 16px; text-align: center; margin: 16px; border: 1px solid black)
<iframe width="100%" height="475" src="https://stackblitz.com/edit/react-rqdprk?embed=1&file=Components/Char.js" frameborder="0"></iframe> 
5. Render a list of CharComponents where each CharComponent receives a different letter of the entered text (in the inital input field) as a prop
6. When you click a CharComponent, it should be removed from the entered text.

<iframe width="100%" height="475" src="https://stackblitz.com/edit/react-rqdprk?embed=1&file=App.js" frameborder="0"></iframe>

Here are some more articles about lists and conditional rendering:
Conditional Rendering: https://reactjs.org/docs/conditional-rendering.html
Lists & Keys: https://reactjs.org/docs/lists-and-keys.html




