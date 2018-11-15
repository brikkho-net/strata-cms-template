---
date: 2018-12-22T20:04:40.407Z
title: How react renders the DOM
---
Render compares virtual DOM's in React; it compares the Old Virtual DOM VS Re-rendered Virtual DOM.  React keeps 2 copies of the DOM. 
It's much faster than updating the 'real' DOM.  Why? Because updating the real DOM is expensive. 

The Render() doesn't always immediately update "real" DOM.  If no differences then it doesn't touch the "real" DOM; otherwise if there are differences then update "real" DOM.  

When you use React, at a single point in time you can think of the render() function as creating a tree of React elements. On the next state or props update, that render() function will return a different tree of React elements. React then needs to figure out how to efficiently update the UI to match the most recent tree.

 
