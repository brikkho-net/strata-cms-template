---
date: 2016-12-22T20:04:40.407Z
title: Passing Data Between Components in Angular
---
Passing data between different components is very similar to <a href="http://www.moodley.ca/post/how-components-communicate-in-vuejs/">VueJS</a>. 
Both use a publisher/subscriber pattern.  

Below we will demonstate how to accomplish this:
1. Create three new components: GameControl, Odd and Even
2. The GameControl Component should have buttons to start and stop the game
3. When starting the game, an event (holding a incrementing number) should get emitted each second (ref = setInterval())
4. The event should be listenable from outside the component.
5. When stopping the game, no more events should get emitted (clearInterval(ref))
6. A new Odd component should get created for every odd number emitted, the same should happen for the
Even Component (on even numbers)
7. Simply output Odd - Number or Even - Number in the two components.
8. Style the element (e.g. paragraph) holding your output text differently in both component


<iframe width="600" height="315" src="https://stackblitz.com/edit/angular-k2qeaz?embed=1&file=src/index.html" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
