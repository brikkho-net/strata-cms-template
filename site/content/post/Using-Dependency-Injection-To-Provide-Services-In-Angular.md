---
date: 2016-12-22T20:04:40.407Z
title: Using Dependency Injection To Provide Services In Angular
---
What are services in Angular.  Its just another class.  Its a central repository to centralize our code and prevent code duplication.
Common scenarios are logging functions and accessing data.

We can use Dependency Injection to inject our service into the Component.
When creating a service, we have to let Angular know about our LoggingService.
A service allows us to follow the DRY principle which is Don't Repeat Yourself.

In the Component, we have to use the constructor to inject the service.

constructor(private logService: LoggingService)

After this we have to let Angular know about this service by adding it to the providers attribute.

At this point, Angular will find the service and inject it into our Component when it is created, the logService and call its methods directly in our class.

Angular provides a Hierachical Injector in the way it provides services.  If you inject the service in your child component, only the single instance will be available.

In order to have the same instance shared across your app, you have to inject it from the parent component.

We can do this in App.Component.


