---
date: 2016-12-22T20:04:40.407Z
title: Creating Forms In Angular Using Reactive Forms
---
There are 2 ways to build form in Angular, you can use Reactive Forms or Template Driven Forms.  Using Reactive forms, you can control the forms using code. <br />
 <br />
 Create a Form with the following Controls and Validators <br />
          1) Sales Lead Name (should not be empty) <br />
          2) Mail (should not be a empty and a valid email) <br />
          3) Lead Status Dropdown, with three values: 'Hot', 'Warm', 'Cold' <br />
          4) Submit Button <br />
 <br />
          Add your own Validator which doesn't allow "Test" as a Sales Lead Name <br /> <br />
 <br />
          In addition, implement that Validator as an async Validator (replace the other one) <br />
 <br />
          Upon submitting the form, simply print the value to the console <br />

 
