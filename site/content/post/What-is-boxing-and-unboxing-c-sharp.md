---
date: 2016-12-22T20:04:40.407Z
title: What is boxing and unboxing in C#
---
C# Type System contains three Types:
1. Value Types
2. Reference Types 
3. Pointer Types. 

C# allows us to convert a Value Type to a Reference Type, and back again to Value Types. The operation of Converting a Value Type to a Reference Type is called Boxing and the reverse operation is called Unboxing.

 
<table>
  <caption>Difference between Dispose &amp; Finalize Method</caption>
<tr>
  <th>
    Boxing
  </th>
  <th>
    Unboxing
  </th>
</tr>
  <tr>
  <td>
      1:	int Val = 1; 
  </td>
  <td>
       1:	int Val = 1;
  </td>
</tr>
    <tr>
  <td> 
      2:	Object Obj = Val; //Boxing
  </td>
  <td> 
       2:	Object Obj = Val; //Boxing 
  </td>
</tr>
   <tr>
  <td> 
  </td>
  <td> 
       3:	int i = (int)Obj; //Unboxing
  </td>
</tr>
</table>
