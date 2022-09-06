# How To: Using CRC Cards and UML Diagrams in Program Design
Before writing code for a complex problem, you need to design a solution. The methodology introduced in this chapter suggests that you follow a design process that is composed of the following tasks:

* Discover classes.
* Determine the responsibilities of each class.
* Describe the relationships between the classes.

CRC cards and UML diagrams help you discover and record this information.

`Step 1` Discover classes.

Highlight the nouns in the problem description. Make a list of the nouns. Cross out those that don’t seem to be reasonable candidates for classes.

`Step 2` Discover responsibilities.

Make a list of the major tasks that your system needs to fulfill. From those tasks, pick one that is not trivial and that is intuitive to you. Find a class that is responsible for carrying out that task. Make an index card and write the name and the task on it. Now ask yourself how an object of the class can carry out the task. It probably needs help from other objects. Then make CRC cards for the classes to which those objects belong and write the responsibilities on them.

Don’t be afraid to cross out, move, split, or merge responsibilities. Rip up cards if they become too messy. This is an informal process.

You are done when you have walked through all major tasks and are satisfied that they can all be solved with the classes and responsibilities that you discovered.

`Step 3` Describe relationships.

Make a class diagram that shows the relationships between all the classes that you discovered.

Start with inheritance—the is-a relationship between classes. Is any class a specialization of another? If so, draw inheritance arrows. Keep in mind that many designs, especially for simple programs, don’t use inheritance extensively.

The “collaborators” column of the CRC card tells you which classes are used by that class. Draw dependency arrows for the collaborators on the CRC cards.

Some dependency relationships give rise to aggregations. For each of the dependency relationships, ask yourself: How does the object locate its collaborator? Does it navigate to it directly because it stores a reference? In that case, draw an aggregation arrow. Or is the collaborator a method parameter variable or return value? Then simply draw a dependency arrow.



## Thanks for watching!

If you liked my coding then follow me on my [Instagram](https://www.instagram.com/fabianzelayahn/) account or [GitHub](https://github.com/fabianzelaya) account.

<img src="https://ucarecdn.com/d1a85e63-35f9-41d7-b758-ff05742057d1/GitHub_Black_Signature.png" width="240" height="79.63" />
