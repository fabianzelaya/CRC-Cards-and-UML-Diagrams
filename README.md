# How To: Using CRC Cards and UML Diagrams in Program Design
Before writing code for a complex problem, you need to design a solution. The methodology introduced in this chapter suggests that you follow a design process that is composed of the following tasks:

* Discover classes.
* Determine the responsibilities of each class.
* Describe the relationships between the classes.

CRC cards and UML diagrams help you discover and record this information.

`Step 1` **Discover classes.**

Highlight the nouns in the problem description. Make a list of the nouns. Cross out those that don’t seem to be reasonable candidates for classes.

`Step 2` **Discover responsibilities.**

Make a list of the major tasks that your system needs to fulfill. From those tasks, pick one that is not trivial and that is intuitive to you. Find a class that is responsible for carrying out that task. Make an index card and write the name and the task on it. Now ask yourself how an object of the class can carry out the task. It probably needs help from other objects. Then make CRC cards for the classes to which those objects belong and write the responsibilities on them.

Don’t be afraid to cross out, move, split, or merge responsibilities. Rip up cards if they become too messy. This is an informal process.

You are done when you have walked through all major tasks and are satisfied that they can all be solved with the classes and responsibilities that you discovered.

`Step 3` **Describe relationships.**

Make a class diagram that shows the relationships between all the classes that you discovered.

Start with inheritance—the is-a relationship between classes. Is any class a specialization of another? If so, draw inheritance arrows. Keep in mind that many designs, especially for simple programs, don’t use inheritance extensively.

The “collaborators” column of the CRC card tells you which classes are used by that class. Draw dependency arrows for the collaborators on the CRC cards.

Some dependency relationships give rise to aggregations. For each of the dependency relationships, ask yourself: How does the object locate its collaborator? Does it navigate to it directly because it stores a reference? In that case, draw an aggregation arrow. Or is the collaborator a method parameter variable or return value? Then simply draw a dependency arrow.


# Attributes and Methods in UML Diagrams
Sometimes it is useful to indicate class attributes and methods in a class diagram. An attribute is an externally observable property that objects of a class have. For example, `name` and `price` would be attributes of the `Product` class. Usually, attributes correspond to instance variables. But they don’t have to—a class may have a different way of organizing its data. For example, a `GregorianCalendar` object from the Java library has attributes `day`, `month`, and `year`, and it would be appropriate to draw a UML diagram that shows these attributes. However, the class doesn’t actually have instance variables that store these quantities. Instead, it internally represents all dates by counting the milliseconds from January 1, 1970—an implementation detail that a class user certainly doesn’t need to know about. (Definition of **attribute**: A named property that an object is responsible for maintaining.)

You can indicate attributes and methods in a class diagram by dividing a class rectangle into three compartments, with the class name in the top, attributes in the middle, and methods in the bottom (see Figure 11.4.1).

### Figure 11.4.1: Attributes and Methods in a Class Diagram.
![embedded_image_1_ae27ff57-d860-4eee-9163-fedc2b4a980c_UxPnsu3LFPheZgXpTgOa](https://user-images.githubusercontent.com/71942518/188543175-ea861ada-fec8-4143-80d3-3e3fbc1b7ca1.png)

You need not list all attributes and methods in a particular diagram. Just list the ones that are helpful for understanding whatever point you are making with a particular diagram.

Also, don’t list as an attribute what you also draw as an aggregation. If you denote by aggregation the fact that a `Car` has `Tire` objects, don’t add an attribute `tires`.


# Multiplicities
Some designers like to write multiplicities at the end(s) of an aggregation relationship to denote how many objects are aggregated. The notations for the most common multiplicities are:

* any number (zero or more): *
* one or more: 1..*
* zero or one: 0..1
* exactly one: 1

Figure 11.5.1 shows that a customer has one or more bank accounts.

### Figure 11.5.1: An Aggregation Relationship with Multiplicities.
![embedded_image_1_e44aed4e-99c8-4b99-989d-ca98bab2e177_UxPnsu3LFPheZgXpTgOa](https://user-images.githubusercontent.com/71942518/188543660-add8506f-4169-4076-8cfa-38b8d49ec1b3.png)


# Aggregation, Association, and Composition
Some designers find the aggregation or has-a terminology unsatisfactory. For example, consider customers of a bank. Does the bank “have” customers? Do the customers “have” bank accounts, or does the bank “have” them? Which of these “has” relationships should be modeled by aggregation? This line of thinking can lead us to premature implementation decisions.

Early in the design phase, it makes sense to use a more general relationship between classes called association. A class is associated with another if you can navigate from objects of one class to objects of the other class. For example, given a `Bank` object, you can navigate to `Customer` objects, perhaps by accessing an instance variable, or by making a database lookup. (Definition of **association**: A relationship between classes in which one can navigate from objects of one class to objects of the other class, usually by following object references. )

The UML notation for an association relationship is a solid line, with optional arrows that show in which directions you can navigate the relationship. You can also add words to the line ends to further explain the nature of the relationship. Figure 11.6.1 shows that you can navigate from `Bank` objects to `Customer` objects, but you cannot navigate the other way around. That is, in this particular design, the `Customer` class has no mechanism to determine in which banks it keeps its money.

### Figure 11.6.1: An Association Relationship.
![embedded_image_1_bb2defa2-ef37-4325-95ba-94cd7011a46d_UxPnsu3LFPheZgXpTgOa](https://user-images.githubusercontent.com/71942518/188543763-654c2795-d2bc-4418-aed8-78cd47e7e923.png)

The UML standard also recognizes a stronger form of the aggregation relationship called composition, where the aggregated objects do not have an existence independent of the containing object. For example, composition models the relationship between a bank and its accounts. If a bank closes, the account objects cease to exist as well. In the UML notation, composition looks like aggregation with a filled-in diamond, as shown in Figure 11.6.2 (Definition of **composition**: An aggregation relationship where the aggregated objects do not have an existence independent of the containing object.)

### Figure 11.6.2: A Composition Relationship.
![embedded_image_1_72bdb6df-d67d-48a0-b887-ab11f7661bbb_UxPnsu3LFPheZgXpTgOa](https://user-images.githubusercontent.com/71942518/188543816-38d96f0c-a147-4123-a1a9-cfeda9378a5b.png)

Frankly, the differences between aggregation, association, and composition can be confusing, even to experienced designers. If you find the distinction helpful, by all means use the relationship that you find most appropriate. But don’t spend time pondering subtle differences between these concepts. From the practical point of view of a Java programmer, it is useful to know when objects of one class have references to objects of another class. The aggregation or has-a relationship accurately describes this phenomenon.



## Thanks for watching!

If you liked my coding then follow me on my [Instagram](https://www.instagram.com/fabianzelayahn/) account or [GitHub](https://github.com/fabianzelaya) account.

<img src="https://ucarecdn.com/d1a85e63-35f9-41d7-b758-ff05742057d1/GitHub_Black_Signature.png" width="240" height="79.63" />
