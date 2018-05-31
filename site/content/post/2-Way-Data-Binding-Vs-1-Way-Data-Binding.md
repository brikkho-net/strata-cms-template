---
date: 2016-12-22T20:04:40.407Z
title: 2 Way Data Binding Vs 1 Way Data Binding
---
1 Way data binding
Add input using 1 way data binding to the input.  This will update only in a single direction.  If it gets updated anywhere in the component, it will not update because it's not using 2 way data binding. <br />
< p >{{name}}< /p ><br />
< input type="text" class="form-control" (input)="$event" /><br />

2-Way data binding
It will update the value of the input element if we change the variable somewhere else.  In order to use 2 way data binding, we have to import the FormsModule to enable ngModel.  <br />
<input type="text" class="form-control" [(ngModel)]="name" /><br />

Add input using 2 way data binding

