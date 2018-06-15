---
date: 2016-12-22T20:04:40.407Z
title: How to setup Routing in Angular
---
When adding routes in angular, we can separate the routing code into its own file.  We can add a new module call app-routing.module.ts.
Use the angular cli to add a new module.  Type "ng g m app-routing"  This will generate a new module.

Add the following code:

<iframe width="100%" height="475" src="https://stackblitz.com/edit/angular-7r7sej?embed=1&file=src/app/app-routing.module.ts&view=editor" frameborder="0"></iframe>

in the above code, we can add children to each path.  Each child can do separate things such as edit and new functions.
