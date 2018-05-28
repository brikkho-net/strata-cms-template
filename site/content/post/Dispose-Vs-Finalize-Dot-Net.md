---
date: 2016-12-22T20:04:40.407Z
title: Dispose Vs Finalize Dot.Net
---
The difference between the Dispose and Finalize method in .NET are very suttle. Both methods deal with garbage collection (GC).  The .NET Framework provides two methods Finalize and Dispose for releasing unmanaged resources such as:
1. Files
2. Database connections

<table>
  <caption>Difference between Dispose &amp; Finalize Method</caption>
<tr>
  <th>
    Dispose
  </th>
  <th>
      Finalize
  </th>
</tr>
  <tr>
  <td>
    It is used to free unmanaged resources like files, database connections etc. at any time.
  </td>
  <td>
      It can be used to free unmanaged resources (when you implement it) like files, database connections etc. held by an object before that object is destroyed.
  </td>
</tr>
    <tr>
  <td>
    Explicitly, it is called by user code and the class which is implementing dispose method, must has to implement IDisposable interface.
  </td>
  <td>
      Internally, it is called by Garbage Collector and cannot be called by user code.
  </td>
</tr>
    <tr>
  <td>
    It belongs to IDisposable interface.</div><div>It belongs to Object class.
  </td>
  <td>
      It's implemented with the help of destructor in C++ &amp; C#.
  </td>
</tr>
 <tr>
  <td>
    There is no performance costs associated with Dispose method.
  </td>
  <td>
      There is performance costs associated with Finalize method since it doesn't clean the memory immediately and called by GC automatically.
  </td>
</tr>
</table>
<div class="table"> 
 
