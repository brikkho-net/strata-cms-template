---
date: 2018-03-09
title: How components communicate in VueJS
---
<strong>Components in VueJS communicate in a Unidirectional manner</strong>  

<img src="/images/component-communication.jpg" alt="Components in VueJS communicate in a Unidirectional manner" />

<strong>Using Custom Event and Props</strong>

When trying to pass data from Child 1 to the Parent, you have to use the Props method and the Emit method.
You got props  to pass data from a PARENT => CHILD.

You got events ($emit ) to pass data from CHILD => PARENT.
 
 
<strong>Using an Event Bus</strong>
<img src="/images/event-bus-sibling-to-siblin.jpg" alt="Components in VueJS communicate sibling to sibling using event bus" />
When you have two sibling components which you need to communicate with each other: You can use an event bus to pass data from SIBLING => SIBLING.

There is a second strategy where we can use an Event Bus.  Using this strategy, we have to create a listener.  


<style>
img {
    width: 100%;
}
</style>
