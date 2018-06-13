---
date: 2016-12-22T20:04:40.407Z
title: Creating Forms In Angular Using Template Driven Forms
---
There are 2 ways to build form in Angular, you can use Reactive Forms or Template Driven Forms.  Using Template driven forms, you can write templates in the Angular template syntax with the form-specific directives and techniques described in this page.

1.  Make sure the email address is not empty and gets validated for email.
 <input type="email" id="email" class="form-control" email required ngModel name="email">
2.  A dropdown that allows a user to choose different statuses - warm, hot, cold.
  <label for="status">Status</label>
  <select name="status" id="status" ngModel class="form-control">
    <option value="pet" *ngFor="let status of statuses" [value]="status">{{status}}</option>
  </select>
  
  statuses = ['Hot', 'Warm', 'Cold'];
3.  A password field that is not null.
  <label for="password">Password</label>
  <input type="password" id="password" class="form-control" ngModel name="password" required >
  <div [hidden]="password.valid || password.pristine" class="alert alert-danger">
     Password is required
  </div>
4.  A submit button.
 
<iframe width="100%" height="475" src="https://stackblitz.com/edit/angular-ufxm7p?embed=1&file=src/app/app.component.html" frameborder="0"></iframe>

Display a warning message if the form is invalid and was touched.  Display a warning label below each input field letting them know their input is invalid.
 <div [hidden]="!myForm.valid || myForm.touched" class="alert alert-danger">
          Form is not valid
 </div>
After submitting the form, print the form input to the console.
 onSubmit() {
    console.log(this.myForm.value);
  }
When setting up a form, we need to add the following code to the form tag:
<form (ngSubmit)="onSubmit()" #myForm="ngForm">

To access the form values in the component code, we can use the ViewChild method that inherits from NgModel:
@ViewChild("myForm") myForm: NgForm;

<iframe width="100%" height="475" src="https://stackblitz.com/edit/angular-ufxm7p?embed=1&file=src/app/app.component.ts" frameborder="0"></iframe>

