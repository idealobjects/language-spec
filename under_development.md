The file tracks work that is under development. Ideas that are being specced, but not yet added to the main spec will sit here.

## Sets

Sets are ways to define groups of objects. A set can be used to run commands on the entire set of objects.

The purpose of providing sets is as follows:

1. Bulk Operations
2. Aggregation

First, bulk operations. There are going to be many ways in that you will want to update multiple objects with the same value. One example is updating the type on a group of objects with a similar type. There are many others. Either way, it will be important to provide capabilities to perform actions like this in bulk.

Second, aggregation. When looking at a group of objects, you may want to know certain information about the set. For example, in running a simulation, you will want to know how many objects of a certain type are assigned to another.

Sets, if done properly, can provide a very strong way to group and work with objects.
