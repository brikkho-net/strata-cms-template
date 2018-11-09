---
date: 2018-11-22T20:04:40.407Z
title: Create new components that update user input onto screen in ReactJS
---

 
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




