---
date: 2018-12-22T20:04:40.407Z
title: How react renders the DOM
---
Render compares virtual DOM's in React; it compares the Old Virtual DOM VS Re-rendered Virtual DOM.  React keeps 2 copies of the DOM. 
It's much faster than updating the 'real' DOM.  Why? Because updating the real DOM is expensive. 

The Render() doesn't always immediately update "real" DOM.  If no differences then it doesn't touch the "real" DOM; otherwise if there are differences then update "real" DOM.  

 
