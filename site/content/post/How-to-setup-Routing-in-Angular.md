---
date: 2016-12-22T20:04:40.407Z
title: How to setup Routing in Angular
---
When adding routes in angular, we can separate the routing code into its own file.  We can add a new module call app-routing.module.ts.
Use the angular cli to add a new module.  Type "ng g m app-routing"  This will generate a new module.

Add the following code:
 `const appRoutes: Routes = [
    { path: '', component: HomeComponent },
    { path: 'cars', component: CarsComponent, children:
      [
        { path: ':id/:name', component: CarComponent }
      ]
    },
  {
    path: 'boats', component: BoatsComponent, children:
      [
        { path: ':id', component: BoatComponent },
        { path: ':id/edit', component: EditBoatComponent }
      ] },
    { path: 'not-found', component: PageNotFoundComponent },
    { path: '**', redirectTo: '/not-found' }
]
`

in the above code, we can add children to each path.  Each child can do separate things such as edit and new functions.
