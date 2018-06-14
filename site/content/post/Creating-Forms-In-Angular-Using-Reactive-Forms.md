---
date: 2016-12-22T20:04:40.407Z
title: Creating Forms In Angular Using Reactive Forms
---
There are 2 ways to build form in Angular, you can use Reactive Forms or Template Driven Forms.  Using Reactive forms, you can control the forms using code.

 Create a Form with the following Controls and Validators
          1) Sales Lead Name (should not be empty)
          2) Mail (should not be a empty and a valid email)
          3) Lead Status Dropdown, with three values: 'Hot', 'Warm', 'Cold'
          4) Submit Button

          Add your own Validator which doesn't allow "Test" as a Sales Lead Name

          In addition, implement that Validator as an async Validator (replace the other one)

          Upon submitting the form, simply print the value to the console

<iframe width="100%" height="475" src="https://stackblitz.com/edit/angular-ufxm7p?embed=1&file=src/app/app.component.ts" frameborder="0"></iframe>

