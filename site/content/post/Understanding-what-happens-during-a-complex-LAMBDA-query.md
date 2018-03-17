LAMBDA expressions were introduced in C# 3.0 (.NET 3.5) along with LINQ.  The LAMBDA expression is a shorter way of representing anonymous methods using special syntax.

For example, the following anonymous method checks if the customers balance is over $1000:

Anonymous method in C#:
<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/5SccvF" frameborder="0"></iframe>

The above anonymous method can be rewritten using the following:

Lambda Expression in C#:

c => c.Balance > 1000
Below is a more complex LAMBDA expression:
<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/KI5ZpV" frameborder="0"></iframe>
