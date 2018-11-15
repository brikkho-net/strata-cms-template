---
date: 2018-12-22T20:04:40.407Z
title: How react renders the DOM
---
Render compares virtual DOM's in React; it compares the Old Virtual DOM VS Re-rendered Virtual DOM.  React keeps 2 copies of the DOM. 
It's much faster than updating the 'real' DOM.  Why? Because updating the real DOM is expensive. 

The Render() doesn't always immediately update "real" DOM.  If no differences then it doesn't touch the "real" DOM; otherwise if there are differences then update "real" DOM.  

When you use React, at a single point in time you can think of the render() function as creating a tree of React elements. On the next state or props update, that render() function will return a different tree of React elements. React then needs to figure out how to efficiently update the UI to match the most recent tree.

There are some generic solutions to this algorithmic problem of generating the minimum number of operations to transform one tree into another. However, the state of the art algorithms have a complexity in the order of O(n3) where n is the number of elements in the tree.

If we used this in React, displaying 1000 elements would require in the order of one billion comparisons. This is far too expensive. Instead, React implements a heuristic O(n) algorithm based on two assumptions:

Two elements of different types will produce different trees.
The developer can hint at which child elements may be stable across different renders with a key prop.
