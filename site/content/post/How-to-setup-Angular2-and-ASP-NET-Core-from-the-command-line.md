---
date: 2016-12-22T20:04:40.407Z
title: How to setup Angular2 and ASP.NET Core from the command line
---
Setting up Asp.Net Core and Angular2 is actually very easy!  There are several ways to setup a project.

Before we can start using the command line, we need to install the following:

ASP.NET Core installers
npm – $ npm install npm@latest -g
Yeoman – $ npm install -g yo
Step 1:

From the command line install the JavaScript Services generator:

npm install -g yo generator-aspnetcore-spa

Step 2:
Run the generator using the yo aspnetcore-spa command and choose Angular 2 from the list of templates.

Once the generator has completed, it will generate a complete app using asp.net core and angular2.  

You can get the app running using dotnet run.
