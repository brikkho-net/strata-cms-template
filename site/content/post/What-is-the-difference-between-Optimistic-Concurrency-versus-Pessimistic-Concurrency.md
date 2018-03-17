---
date: 2016-12-22T20:04:40.407Z
title: What is the difference between Optimistic Concurrency versus Pessimistic Concurrency
---
Optimistic Locking is a way of versioning your record by add either a date, timestamp or hash.  If there are multiple users updating that record, the software will know if the record has changed based on the hash.  The reason for this is that you have to make sure the version is atomic.  This means that the record hasn’t been updated by another user while you were editing the value.

If the record’s version number has changed, then we can assume it is dirty and you would then abort the transaction and the user can restart the process.

Why would you use Optimistic Locking?

You would use this strategy if you application has a lot of users updating the same records at the same time or if you are using a three-tiered architecture.   If you are using a three tiered architecture then you would not be a maintaining a connection to the database for your session.  Using this architecture, the client cannot maintain a database lock because the connections are taken from a pool.

Pessimistic Locking is when the client can maintain a database lock on the record and you can lock the record exclusively for yourself until you have finished updating the record.  It has better integrity than optimistic locking; however there is major issue with Deadlocks.  In order to use pessimistic locking, you need a direct connection to the database or an externally available transaction ID than can be used independently of the connection.  You would see this design in a two-tierd client server architecture.
