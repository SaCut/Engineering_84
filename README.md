# Interview Preparation

## Tell Me About Yourself

Hello, My name is Saverio, I'm from Italy, and I have a degree in Eastern Languages and Linguistics.

I've always had a passion for technology, so after working as a translator after graduation I decided to redirect my career and
improve my coding skills by following courses online and getting practical experince on actual code.

Since then I've developed many small projects in Python, using various libraries and frameworks, trying to apply common principles
like object oriented programming and readable code with appropriate documentation.

Among the projects I worked on there are image manipulation for object detection, face recognition tools, web scapers and simple
user interfaces.

I've also used Linux desktop for ten years now, so I also have a bit of practive with command line interfaces and virtual machines.

During my Sparta Global training, I was also introduced to database management and queries with SQL, to Agile development and its
principles, and to the use of Scrum frameworks.

I'm very interested in Science and Technology and like to keep updated with the latest news on Artificial Intelligence and Robotics.

### Business Week Questions

#### Question: What is Agile and what are the benefits of implementing it?
* Answer: Agile is a set of principles for software development based on the best practices that have been observed to lead to
consistently better results over the years.
Agile is based on four core principles that define some priorities in opposition to the old way of looking at software development,
and they are:
  * **Individuals and interactions** over processes and tools: the individual skills of the people working on a project should take
  precedence over any weight given to the tools used to manage and develop said projects;
  * **Working software** over comprehensive documentation: the aim of a company is releasing a product, so releasing software that
  can be actually used by the user/customer comes before writing extensive and detailed documentation for said project.
  * **Customer collaboration** over contract negotiation: this principle encourages to look at the customer in a collaborative wiev,
  as that will lead to a better end-result than prioritising the contract and viewing the relation with the customer as adversarial.
  * **Responding to change** over following a plan: adaptability is foundational in agile. The method encourages looking at the code
  in a modular light, to be shaped and rearraged in response to the customer feedback and to whatever need might arise during development.

#### What is DevOps and the what are the benefits of using it?
- Answer: The term DevOps comes from the union of Development and Operations, which means that DevOps evolved as a bridge to mend the gap
between Software development, that often found themselves at odds by working in compartmentalised units. By improving communication and
bringing everyone into the same team, the process becomes far smoother and the product lifecycle is greatly improved.

#### Question: Why did you choose Sparta Global?
- Answer: I chose Sparta Global because, in addition to an impressive growth in recent years and many collaborations with important clients,
they have shown to have top notch training and to follow their Spartans closely throughout the whole consultancy.

#### Question: What is SCRUM and what are the benefits of implementing it?
- Answer: Scrum is a framework in the Agile methodology that aims to improve the work of the team collaborating on a project. It's based on
constant iterations and reviews, by setting recurring sprints and working through them one step at a time. The aim of Scrum is to improve
transparency for the whole team, to make sure that everyone is on the same page and that problems are addressed as soon as possible, and that
the simplicity is maintained and no unecessary work is performed.

#### Question: Where do you see yourself in 2-5 years time
- Answer: In the short term I see myself as working as a Junior DevOps Consultant at Sparta GLobal, but after that I plan on taking advantage
of the experience I've accumulated in this role and progress my career up to Senior in DevOps, or maybe any related opportunities that require
a similar skillset.

### SQL Questions

#### What is a JOIN?
- Answer: A JOIN is an operation that can be performed during a query between two tables in a database, to retrieve data from a combination of
the two. A JOIN requires an ON qualifier, that equates the element of a column from one table with another column from the other table. There
are different kinds of JOIN, like for example LEFT and RIGHT JOIN, that create a subset containing all the elements from (respectively) the left
or right table, filling empty cells from the other table with *NULL*, or INNER JOIN, that only returns rows in which the compared elements are
present in both.

#### What is primary key and foreign key and what are their functions?
- Answers: In a relational database, tables have keys, that is to say entries in some columns, that have the function of linking the tables
together. Primary keys have to respect certain parameters, like being each element of a primary key being unique, never *NULL*, and not change
for the duration of the table. Primary keys can also be simple (made of just one column) or composite (made of more than one column). Foreign
keys in contrast can be repeated, can be *NULL*, and can be changed. Keys are important in defining relations between tables, and can be used to
handle one-to-one relations, one-to-many relations, or many-to-many, through the use of junction tables.

#### Describe DML, DDL, DCL and TCL.
* Answer: The operations possible in SQL can be divided in multiple categories:
    * DML, or Data Manipulation Language, handles the content of tables and can be used to modify or delete rows. The statements associated with
  this level of control of a database are:
        * SELECT, that allows to retrieve information from a table;
        * INSERT, that allows to insert information inside a table;
        * UPDATE, for changing the contents of a pre-existing element;
        * DELETE, for deleting single elements or rows.
    * DDL, or Data Definition Language, that allows to work on the structure of the database itself. The statements of DDL are:
        * CREATE, which allows for the creation of tables;
        * ALTER, which is used to add, delete or modify the columns of a table;
        * DROP, which cancels a table.
        * TRUNCATE, which empties a table of all its contents while leaving its structure intact.
    * DCL, or Data Control Language, which is used to handle the user permissions in a database
        * GRANT, to grant permissions to a user;
        * REVOKE, to revoke permissions.
    * TCL, or Transaction Control Language, that deals with manage the changes to a database. The statements are:
        * COMMIT, to permanently save changes to the database;
        * ROLLBACK, to change the state of the database to a previus savepoint;
        * SAVEPOINT, to save the current state of the database.

#### Describe Normalisation and its first three forms.
* Answer: Database Normalisation is the process of structuring a relational database such that data integrity is maximised and redundancy is reduced.
    * #TODO

#### What is an Entity Relationship Diagram?
- Answer: An Entity Relationship Diagram (ERP) is a graph that visualises the structure of the database in use. It lists the names of the tables,
the columns in each table and their associated data type, the relationships between tables, and the primary and foreign keys. An ERP is essential
for getting a bird's eye view of the database and make any change and query be written much more quickly and efficiently.

### Python and OOP questions

#### What are Git and Github, and why are they useful?
- Answer: Git is a version control system on the user device that allows for version control of the software that one is working on, and it allows
for committing local code to the cloud and rollbacks when needed. Git-hub is an online repository, maily intended for saving, editing, collectively
editing and backing up software on the cloud, in order for the code to be securely stored and available everywhere and to everyone that has been
granted access to it.

![alt text](https://i.imgur.com/0EhJ1Zu.png)

#### What is OOP and Why should we use it
- Answer: Object-Oriented Programming is a programming paradigm in which the code is organised in structures called objects, that contain variables (attributes), and behaviours (methods). OOP follows the Four Pillars to optimise the paradigm.

#### What are the benefits of OOP?
- Answer: The main advantage of OOP is that it avoids rewriting the code multiple times (DRY), making software development much faster, and allows for easy scalability: objects can be shared easily between developers without any understanding of the underlying code necessary, they work like black-boxes in which values can be entered and a certain result is returned at the end. A common example of this is importing modules (shared between the community) in Python, modules that are often orders of magnitude more optimised than what would be possible to produce within a larger project, and that are maintained and adapted to work in multiple (if not all) versions of the coding environment.

#### What is an API and why should we use it?
- Answer: An Application Programming Interface is an interface that defines interactions between multiple modules or applications. It defines the kinds of calls or requests that can be made, how to make them, the data formats that should be used, the conventions to follow, etc. It can also provide extension mechanisms so that users can extend existing functionality in various ways and to varying degrees. APIs are fundamental for software interactions with imported modules.

#### What are Python packages and modules
- Answer: packages and modules in Python are bundles of pre-written code that allow the developer to import the functionality they cover without needing to rewrite the code from scratch. The Python environment is absolutely flooded with various packages and modules, and they cover tools to do basically anything
that could be considered general use.

#### what is pip?
- Answer: pip os Python's package manager. It allows to find, install and manage Python packages easily from the command line.

#### What are four pillars of OOP and why should we use them?
- Answer: the Four Pillars of OOP are:
* **Abstraction**. An object is OOP has to be a self-contained block of code as much as possible. The ideal object is like a black-box in which the user can 
input certain values, and get back some results obtained through the manipulation of those values. The user should never need to see or worry about what's inside
the object, it should just work.
* **Inheritance**. In OOP objects have attributes and methods. Inehritance is the process by which an object (called child) can receive the attributes and methods
of another object (called parent).
* **Encapsulation**. As previously said, objects in OOP should be self-contained. Encapsulation takes this concept a step further, so that the internal features
of an object are not only far-removed, but actively hidden. This is useful when, for some reason, the data inside of an object has to remain private.
* **Polymorphism** is a simple concept. Like in the animal kingdom children can inherit sligtly different features than those of their parents, so in Object
Oriented Programming it's possible to modify or overwrite attributes and methods that have been inherited from a parent object to the child.
