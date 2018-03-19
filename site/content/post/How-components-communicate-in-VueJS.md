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

<strong>Props</strong>

Passing Data with Props

Every component instance has its own isolated scope. This means you cannot (and should not) directly reference parent data in a child component’s template. Data can be passed down to child components using props.



A prop is a custom attribute for passing information from parent components. A child component needs to explicitly declare the props it expects to receive using the props option:

 
Custom Events
We have learned that the parent can pass data down to the child using props, but how do we communicate back to the parent when something happens? This is where Vue’s custom event system comes in.

Using v-on with Custom Events
Every Vue instance implements an events interface, which means it can:

Listen to an event using $on(eventName)

Trigger an event using $emit(eventName, optionalPayload)

Note that Vue’s event system is different from the browser’s EventTarget API. Though they work similarly, $on and $emit are not aliases for addEventListener and dispatchEvent.

In addition, a parent component can listen to the events emitted from a child component using v-on directly in the template where the child component is used.

You cannot use $on to listen to events emitted by children. You must use v-on directly in the template, as in the example below.

Here’s an example:

 
In this example, it’s important to note that the child component is still completely decoupled from what happens outside of it. All it does is report information about its own activity, just in case a parent component might care.
  
In this second example, it’s important to note that the child component is still completely decoupled from what happens outside of it. All it does is report information about its own activity including a payload data into event emitter, just in case a parent component might care.
 
 
<strong>Using an Event Bus</strong>
<img src="/images/event-bus-sibling-to-siblin.jpg" alt="Components in VueJS communicate sibling to sibling using event bus" />
When you have two sibling components which you need to communicate with each other: You can use an event bus to pass data from SIBLING => SIBLING.

There is a second strategy where we can use an Event Bus.  Using this strategy, we have to create a listener.  

Non Parent-Child Communication
Sometimes two components may need to communicate with one-another but they are not parent/child to each other. In simple scenarios, you can use an empty Vue instance as a central event bus:

<figure class="highlight js"><table><tbody><tr><td class="code"><pre><span class="line"><span class="keyword">var</span> bus = <span class="keyword">new</span> Vue()</span><br></pre></td></tr></tbody></table></figure>

<figure class="highlight js"><table><tbody><tr><td class="code"><pre><span class="line"><span class="comment">// in component A's method</span></span><br><span class="line">bus.$emit(<span class="string">'id-selected'</span>, <span class="number">1</span>)</span><br></pre></td></tr></tbody></table></figure>

<figure class="highlight js"><table><tbody><tr><td class="code"><pre><span class="line"><span class="comment">// in component B's created hook</span></span><br><span class="line">bus.$on(<span class="string">'id-selected'</span>, <span class="function"><span class="keyword">function</span> (<span class="params">id</span>) </span>{</span><br><span class="line">  <span class="comment">// ...</span></span><br><span class="line">})</span><br></pre></td></tr></tbody></table></figure>

In more complex cases, you should consider employing a dedicated state-management pattern.

State Management

Official Flux-Like Implementation
 
<img src="/images/state.png" alt="State Management" />

Large applications can often grow in complexity, due to multiple pieces of state scattered across many components and the interactions between them. To solve this problem, Vue offers vuex: our own Elm-inspired state management library. It even integrates into vue-devtools, providing zero-setup access to time travel.

Useful Links:

Official Docs - Props: http://vuejs.org/guide/components.html#Props

Official Docs - Custom Events: http://vuejs.org/guide/components.html#Custom-Events

Official Docs - Non-Parent-Child Communication: http://vuejs.org/guide/components.html#Non-Parent-Child-Communication

<style>
img {
    width: 100%;
}
</style>
