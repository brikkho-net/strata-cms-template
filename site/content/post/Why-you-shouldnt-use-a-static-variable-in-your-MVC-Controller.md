---
date: 2016-12-22T20:04:40.407Z
title: Why you shouldn’t use a static variable in your MVC Controller
---
I recently came across an interesting situation where I used a static variable in a controller and it caused some issues.  The problem with statics variables is that they are not thread safe meaning that they could potentially be executed by multiple threads.

This is an issue because different users could access other users information if it is stored in a static variable.
