---
date: 2016-12-22T20:04:40.407Z
title: Whats the difference between IEnumerable and IQueryable?
---
The main difference between the 2 is that of efficiency:

IEnumerable will return all the records at once.
IQueryable will return only records that you want based on a filter that executes on the server.
How does each work?

Let’s assume that you have a customer table with all your customer’s information with about 10000 clients.

If you use IEnumerable to get the first 10 customers you end up loading all 10000 and then selecting the first 10.
With IQueryable you only select the first 10
Below is an example on the 2 main differences using C#:

static void Main(string[] args)
{
    using (var db = new Context())
    {
        IEnumerable<Customer> customers = db.Customers.Take(10).ToList();
        // ToList() executes the query straight away
        // All the list of customers are loaded into memory (10000 customers )
        // After that, only the first 6 are selected
        IQueryable<Customer> _customers = db.Customers.Take(10).ToList();
        // ToList() executes the query straight away
        // The first 6 customers are loaded into memory
    }            
}
**What is the use of IEnumerator in C#?

IEnumerable is an interface that defines one method GetEnumerator which returns an IEnumerator interface, this in turn allows readonly access to a collection.  A collection that implements IEnumerable can be used with a foreach statement.

**What is IQueryable in C#?

IQueryable is an interface that implements IEnumerable (and because it implements IEnumerable it means that it allows you to iterate over a collection plus some more) IQueryable takes Expression objects instead of delegates (which is what IEnumerable takes)

When can I use IEnumerable?
When you want to iterate over a collection (List, Arrays, etc.)
When you want to get all the results from your query and apply any further filtering once your collection has been loaded in memory.
When you are using LINQ to XML or LINQ to Object.
When can I use IQueryable?
When you want to iterate over a collection (same as IEnumerable)
When you want to work with data from out-memory, such as a database, a web service etc
When you want to apply a filter to your query BEFORE the query is executed (this can save you heaps of resources)
When Lazy loading is needed (you only get what you need, not the entire list of records)
 
