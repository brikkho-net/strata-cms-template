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

<div id="counter-event-example">
  <p>{{ total }}</p>
  <button-counter v-on:increment="incrementTotal"></button-counter>
  <button-counter v-on:increment="incrementTotal"></button-counter>
</div>
Vue.component('button-counter', {
  template: '<button v-on:click="incrementCounter">{{ counter }}</button>',
  data: function () {
    return {
      counter: 0
    }
  },
  methods: {
    incrementCounter: function () {
      this.counter += 1
      this.$emit('increment')
    }
  },
})

new Vue({
  el: '#counter-event-example',
  data: {
    total: 0
  },
  methods: {
    incrementTotal: function () {
      this.total += 1
    }
  }
})

In this example, it’s important to note that the child component is still completely decoupled from what happens outside of it. All it does is report information about its own activity, just in case a parent component might care.

Here’s an example on how to use payload data:

<div id="message-event-example" class="demo">
  <p v-for="msg in messages">{{ msg }}</p>
  <button-message v-on:message="handleMessage"></button-message>
</div>
Vue.component('button-message', {
  template: `<div>
    <input type="text" v-model="message" />
    <button v-on:click="handleSendMessage">Send</button>
  </div>`,
  data: function () {
    return {
      message: 'test message'
    }
  },
  methods: {
    handleSendMessage: function () {
      this.$emit('message', { message: this.message })
    }
  }
})

new Vue({
  el: '#message-event-example',
  data: {
    messages: []
  },
  methods: {
    handleMessage: function (payload) {
      this.messages.push(payload.message)
    }
  }
})
test message
In this second example, it’s important to note that the child component is still completely decoupled from what happens outside of it. All it does is report information about its own activity including a payload data into event emitter, just in case a parent component might care.
 
 
<strong>Using an Event Bus</strong>
<img src="/images/event-bus-sibling-to-siblin.jpg" alt="Components in VueJS communicate sibling to sibling using event bus" />
When you have two sibling components which you need to communicate with each other: You can use an event bus to pass data from SIBLING => SIBLING.

There is a second strategy where we can use an Event Bus.  Using this strategy, we have to create a listener.  

Non Parent-Child Communication
Sometimes two components may need to communicate with one-another but they are not parent/child to each other. In simple scenarios, you can use an empty Vue instance as a central event bus:

var bus = new Vue()
// in component A's method
bus.$emit('id-selected', 1)
// in component B's created hook
bus.$on('id-selected', function (id) {
  // ...
})

In more complex cases, you should consider employing a dedicated state-management pattern.

Useful Links:

Official Docs - Props: http://vuejs.org/guide/components.html#Props
Official Docs - Custom Events: http://vuejs.org/guide/components.html#Custom-Events
Official Docs - Non-Parent-Child Communication: http://vuejs.org/guide/components.html#Non-Parent-Child-Communication

<style>
img {
    width: 100%;
}
</style>
