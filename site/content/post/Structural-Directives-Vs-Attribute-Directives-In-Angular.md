---
date: 2016-12-22T20:04:40.407Z
title: Structural Directives Vs Attribute Directives In Angular
---
What are directives in Angular?
Directives are instructions in the DOM.  Components are directives; however, they have a template.
We typically add directives with attribute style.  

@Directive({
  selector: '[warningalert]'
})

export class WarningAlertDirective {

}

Structural Directive
*ngIf is a structural directive because it changes the structure of the dom.

Attribute Directives
ngStyle allows us to dynamically update styles.
< p [ngStyle]="{backgroundColor:getColor()}" >

< div ngClass=""></div>

property binding = []

 
<h2>Add A button which says 'Display'</h2>
< button type="text" class="btn btn-primary" (click)="toggleFn()" >Display< /button >
 

<h2>Add a paragraph about Wakanda</h2>
        
< p *ngIf="toggle">Wakanda is a city in Africa that was made famous by its large stockpiles of vibranium< /p>

<h2>Toggle the displaying of that paragraph with the button created in the first step</h2>
        
<h2>Log all button clicks in an array and output that array below the paragraph above< /h2>
< ul>
  < li  *ngFor="let click of btnClicks; let i = index">
  {{i}} {{click}}
  < /li>
< /ul>
<h2>Starting at the 2nd log item, give all future log items a blue background (via ngStyle) and white color (ngClass)</h2>
< ul>
  < li [ngClass]="i>5 ? 'blue': ''" *ngFor="let click of btnClicks; let i = index">
  {{i}} {{click}}
  < /li>
< /ul>      
Below is the component code:


<iframe width="560" height="315" src="https://stackblitz.com/edit/angular-1jaqa9?embed=1&file=src/app/wakanda/wakanda.component.html" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

 
