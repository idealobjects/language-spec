The file tracks work that is under development. Ideas that are being specced, but not yet added to the main spec will sit here.

## Sets

Sets are ways to define groups of objects. A set can be used to run commands on the entire set of objects.

The purpose of providing sets is as follows:

1. Bulk Operations
2. Aggregation

First, bulk operations. There are going to be many ways in that you will want to update multiple objects with the same value. One example is updating the type on a group of objects with a similar type. There are many others. Either way, it will be important to provide capabilities to perform actions like this in bulk.

Second, aggregation. When looking at a group of objects, you may want to know certain information about the set. For example, in running a simulation, you will want to know how many objects of a certain type are assigned to another.

Sets, if done properly, can provide a very strong way to group and work with objects. Fitting this into the language could be difficult. If that provdes challenging, or ruining, it could be moved as an external concept and not part of the language spec.

### Queries

The first thing that is needed is a way to write a query that finds objects and builds a set. We are calling this query for now, but could enter a different name in the long term, but that word captures what I'm looking for right now.

There are a couple of ways that this can be defined. The first that comes to mind is a SQL-like query language. Writing that in a way that fits in the spirit of the language spec. Another idea is to create a find and reduce mechanism. No matter way, creating this as a sort of pipeline -- like modding a text document via a unix command line -- will be the best way to move this forward.
