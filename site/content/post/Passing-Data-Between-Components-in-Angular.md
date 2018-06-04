---
date: 2016-12-22T20:04:40.407Z
title: Passing Data Between Components in Angular
---
Passing data between different components is very similar to <a href="http://www.moodley.ca/post/how-components-communicate-in-vuejs/">VueJS</a>. 
Both use a publisher/subscriber pattern.  

Below we will demonstate how to accomplish this:
 
  <h2>1. Create three new components: GameControl, Odd and Even</h2>  
  <iframe width="600" height="315" src="https://stackblitz.com/edit/angular-k2qeaz?embed=1&file=src/app/game-control/game-control.component.ts&view=editor" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  <h2>2. The GameControl Component should have buttons to start and stop the game</h2>
    <iframe width="600" height="315" src="https://stackblitz.com/edit/angular-k2qeaz?embed=1&file=src/app/game-control/game-control.component.html&view=editor" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
  <h2>3. When starting the game, an event (holding a incrementing number) should get emitted each second (ref = setInterval())</h2>
    
  gameNumber = 0;
  interval;
  constructor() {}

  ngOnInit() {}

  startGame() {
    this.interval = setInterval(() => {
      this.gameNumber++;
      this.sendNumber.emit(this.gameNumber);
    }, 1000);
  }

 
  <h2>4. The event should be listenable from outside the component.</h2>
  @Output() sendNumber = new EventEmitter<number>();
  <h2>5. When stopping the game, no more events should get emitted (clearInterval(ref))</h2>
  stopGame() {
    clearInterval(this.interval);
  }
  <h2>6. A new Odd component should get created for every odd number emitted, the same should happen for the Even Component (on even numbers)</h2>
  @Input() element: { incrementingValue: number };
  <h2>7. Simply output Odd - Number or Even - Number in the two components.</h2>
 < p *ngIf="element % 2 == false" >
  Odd - NUMBER
< /p >

< p *ngIf="element % 2">
 even - NUMBER
< /p >
 
  <h2>8. Style the element (e.g. paragraph) holding your output text differently in both component</h2>
  p {
  color: blue;
}


<iframe width="600" height="315" src="https://stackblitz.com/edit/angular-k2qeaz?embed=1&file=src/index.html" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
