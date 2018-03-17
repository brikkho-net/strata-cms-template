---
date: 2016-09-09T10:24:16-04:00
title: How to build Reactive Forms in Angular2
---


When building forms using the Reactive approach the component class is in charge.

In order to implement this we have to:

Create a property for the root FormGroup.
Create the FormGroup instance.
Pass in each FormControl instance.
Here is an example of how to implement this using typescript:

ngOnInit():  void(){

this.contactForm = new FormGroup({

firstName: new FormControl(),

lastName: new FormControl(),

email: new FormControl(),

sendCatalog: new FormControl(true),

});

}

The above code is not very efficient.  We can optimize it using the FormBuilder.

In order to use the FormBuilder, we have to do the following:

Import FormBuilder.
Inject the FormBuilder Instance.
Use the FormBuilder instance.
ngOnInit():  void(){

this.contactForm = this.fb.group({

firstName: ”,

lastName: ”,

email: ”,

sendCatalog: true,

});

}

Before we can use the FormBuilder, we have to pull them into our Angular Module.

We have to do the following:

Import the ReactiveFormsModule
Add ReactiveFormsModule to the imports array.
@ngModule({

imports: [

BrowserModule,

ReactiveFormsModule

],

declaraions:[

AppComponent,

ContactComponent

],

bootstrap: [AppComponent]

})

export class AppModule  {}

The next step would be to bind the form element to the FormGroup property.

<form class=’form-horizon’ (ngSubmit)=”save()” [formGroup] = “ccontactForm”>

The second step is to bind each input element to its associated FormControl:

<input class=”form-control” id=”firstNameId” type=”text” placeholder=”First Name (required)” formControlName=”firstName” />

After doing all of this we now have a fully functioning reactive control!

