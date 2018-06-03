---
date: 2016-12-22T20:04:40.407Z
title: Understanding Angular Lifecycle Events
---
Angular calls lifecycle hook methods on directives and components as it creates, changes, and destroys them. Angular creates it, renders it, creates and renders its children, checks it when its data-bound properties change, and destroys it before removing it from the DOM.

<table width="100%">
  <colgroup><col width="20%">
  <col width="80%">
  </colgroup><tbody><tr>
    <th>Hook</th>
    <th>Purpose and Timing</th>
  </tr>
  <tr style="vertical-align:top">
    <td>
      <code>ngOnChanges()</code>
    </td>
    <td>
<p>      Respond when Angular (re)sets data-bound input properties.
The method receives a <code><a href="api/core/SimpleChanges" class="code-anchor">SimpleChanges</a></code> object of current and previous property values.</p>
<p>      Called before <code>ngOnInit()</code> and whenever one or more data-bound input properties change.</p>
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      <code>ngOnInit()</code>
    </td>
    <td>
<p>      Initialize the directive/component after Angular first displays the data-bound properties
and sets the directive/component's input properties.</p>
<p>      Called <em>once</em>, after the <em>first</em> <code>ngOnChanges()</code>.</p>
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      <code>ngDoCheck()</code>
    </td>
    <td>
<p>      Detect and act upon changes that Angular can't or won't detect on its own.</p>
<p>      Called during every change detection run, immediately after <code>ngOnChanges()</code> and <code>ngOnInit()</code>.</p>
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      <code>ngAfterContentInit()</code>
    </td>
    <td>
<p>      Respond after Angular projects external content into the component's view / the view that a directive is in.</p>
<p>      Called <em>once</em> after the first <code>ngDoCheck()</code>.</p>
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      <code>ngAfterContentChecked()</code>
    </td>
    <td>
<p>      Respond after Angular checks the content projected into the directive/component.</p>
<p>      Called after the <code>ngAfterContentInit()</code> and every subsequent <code>ngDoCheck()</code>.</p>
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      <code>ngAfterViewInit()</code>
    </td>
    <td>
<p>      Respond after Angular initializes the component's views and child views / the view that a directive is in.</p>
<p>      Called <em>once</em> after the first <code>ngAfterContentChecked()</code>.</p>
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      <code>ngAfterViewChecked()</code>
    </td>
    <td>
<p>      Respond after Angular checks the component's views and child views / the view that a directive is in.</p>
<p>      Called after the <code>ngAfterViewInit</code> and every subsequent <code>ngAfterContentChecked()</code>.</p>
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      <code>ngOnDestroy()</code>
    </td>
    <td>
<p>      Cleanup just before Angular destroys the directive/component.
Unsubscribe Observables and detach event handlers to avoid memory leaks.</p>
<p>      Called <em>just before</em> Angular destroys the directive/component.</p>
    </td>
  </tr>
</tbody></table>
