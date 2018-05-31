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

<ul>
        <li>Add A button which says 'Display'</li>
        <li>Add a paragraph about Wakanda</li>
        <li>Toggle the displaying of that paragraph with the button created in the first step</li>
        <li>Log all button clicks in an array and output that array below the paragraph above</li>
        <li>Starting at the 2nd log item, give all future log items a blue background (via ngStyle) and white color (ngClass)</li>
</ul>
