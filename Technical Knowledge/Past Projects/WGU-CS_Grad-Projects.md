# What types of C++ projects have you worked on? What concepts did you implement?
"The goal of this project was to create a student roster system that stores student data like name, ID, contact info, grades, and degree program. I created two classes - a Student class to represent each student's data, and a Roster class to manage operations on the roster.

The Student class encapsulates all the data for an individual student like first name, last name, age, list of days to complete each course, degree program, etc. It has accessor methods to get these data fields, mutator methods to modify them, a constructor to initialize a new Student, and a print method to display the data.

The Roster class stores an array of Student object pointers to represent all the students. It has methods to add and remove students, print out info on all students, calculate averages, validate emails, and print students by degree program.

Key things I learned were:

* Using accessors and mutators to control access to class data members
* Working with objects and pointers
* Parsing input strings to initialize class objects
* Writing code in a modular, reusable way

Some ways I could improve this further are:

* Adding more validation logic
* Using a database instead of hard-coded array
* Building out a full GUI instead of just console output

--------
### Glossary
**Class** - A user-defined data type that encapsulates data and functions operating on that data.

**Object** - An instance of a class.

**Encapsulation** - The grouping of related data and functions into an object; a key concept in object-oriented programming.

**Accessor** - A type of class member function used to retrieve the value of a private data member. Also called a getter.

**Mutator** - A type of class member function used to set or modify the value of a private data member. Also called a setter.

**Constructor** - A special class member function that is automatically called when an object is instantiated to initialize it.

**Pointer** - A variable that stores the memory address of another object or variable.

**Array** - A numbered sequence of elements, all with the same type. Arrays allow random access to elements.

**Parse** - To analyze and process an input string to break it into tokens/pieces for usage in a program.

**Modular Code** - Code that is logically broken down into functions and modules that have specific purposes and can be reused.

**Reusable Code** - Code that is written in a generalized way to be used across multiple contexts. Reusable code reduces duplication.

**GUI - Graphical User Interface** - A visual way of interacting with a computer program, opposed to text-based UIs. GUIs have graphical icons, menus, etc.

--------

# What types of SQL projects have you worked on?

"For this project, I had to develop a real-world business analysis report using a DVD rental database in PostgreSQL. The goal was to transform the raw data into easy-to-understand tables and insights.

I designed a report focused on dvd rental patterns across store locations and genres over time. The detailed table contained granular rental data including rental date, store id, inventory id, customer id, return date etc. This supported in-depth analysis.

The summary table aggregated the data by month, location and genre, calculating total rentals and average rental duration. This enabled high-level insights to answer questions like what genres perform best in which locations and months.

I implemented SQL functions to transform the raw data, like converting Y/N flag values into Yes/No strings for readability. Triggers ensured the summary table automatically updated when the detail table was modified. Stored procedures allowed refreshing all data on a schedule.

By using PostgreSQL features like functions, triggers and stored procedures, I created an automated reporting system that provides valuable rental insights for data-driven decision making. The scheduled refresh ensures data is always current.

Going forward, I could enhance by tracking revenue data, implementing dashboards for self-service analysis, and adding machine learning for forecasting and pattern detection."

--------
### Glossary

**Query** - A request for data from a database table.

**Function** - A reusable block of SQL code that performs a specific task.

**Trigger** - A special stored procedure that runs automatically in response to an insert, update or delete event in a database table.

**Stored Procedure** - A reusable and executable SQL code block stored on the database server.


--------

# What types of Python projects have you worked on?

"The goal of this project was to create an efficient routing and scheduling program for a parcel delivery company's trucks. I had to optimize deliveries for 3 trucks across 40 packages per day in Salt Lake City, ensuring all packages were delivered on time within certain constraints.

The inputs included a package data file with delivery details for each package, a distance table with mileage between locations, and a city map.

I designed a algorithm that assigned packages to trucks based on delivery deadlines and locations. It used a hash table to allow fast lookups of package data.

The solution interface displays real-time delivery status and mileage for monitoring. It also meets requirements like delivering incorrectly addressed packages once updated address is known.

The algorithm succeeded in keeping total daily mileage under 140 miles while meeting all delivery promises.

Key things I learned were:

* Optimizing schedules and routes with constraints
* Implementing custom data structures like hash tables
* Writing extensible code with object oriented principles

If I were to further improve this, ideas are:

* Incorporate traffic data to better plan routes
* Add functionality for scheduling additional trucks as needed"

--------
### Glossary

**Algorithm** - A logical step-by-step procedure for solving a problem or optimizing a process.

**Route Optimization** - The process of determining the most efficient routes based on constraints such as total distance, delivery deadlines, vehicle capacity etc.

**Hash Table** - A data structure that maps unique keys to values for efficient lookup and access.

**Distance Matrix** - A table containing mileage between different location pairs. Helps calculate optimized routes.

**Interface** - The user-facing part of a software system for viewing data and accessing functionality.

**Real-time Tracking** - Displaying the current, up-to-date status and location of entities like vehicles or packages.

**Constraints** - Limits or conditions that solutions must satisfy, like maximum distance or delivery deadlines.

**Extensibility** - Designing software that is adaptable for enhancing functionality or scale in the future.

**Object Oriented Programming** - A programming paradigm based on objects that contain data and behaviors defined by class templates.

--------

# Java Frameworks

The goal of this project was to customize an existing inventory management web application for a specific customer's needs. The customer sells products made up of multiple component parts.

To start, I cloned the provided Spring/Java codebase and set up version control with Git. I documented my changes in the README.

First, I customized the HTML user interface - I updated the shop name, product names, and part names to match my chosen customer. I also added an "About" page to describe the company.

Next, I populated the database with sample data - 5 products made up of 5 parts. I ensured no duplicate parts could be added and handled that case by creating "multi-pack" groupings.

Then I added a "Buy Now" button to the product listings that decrements the inventory when clicked. It displays success/failure messages to the user.

A key customization was enhancing part tracking. I added max/min inventory fields and integrated those into the UI forms and validation logic. The app now prevents out-of-range part quantities.

Speaking to process - I used Git for version control, splitting work into small commits associated with prompt tasks. I leveraged unit testing on the new inventory fields. And I tweaked the data persistence layer as needed throughout.

In summary, I took an existing inventory system and customized it to meet a fictional customer's specifications by altering the UI, adding business logic, expanding data modeling, and enhancing validation. My changes demonstrated core software development and maintenance skills.

# Java
The goal was to migrate a critical part of a 1990s vintage vacation booking system to a modern Spring framework, improving reliability and maintainability.

I started by initializing a Spring Boot project and setting up persistence with JPA/Hibernate and MySQL. I structured the codebase into separate controller, service, DAO and entity layers.

A key task was modeling the domain -  I created entity classes for Customer, VacationPackage, Excursion etc. based on the provided UML diagram. I enabled CRUD repositories for these using Spring Data REST.

On the service layer, I wrote a checkout workflow that handles cart and order abstractions. The controllers expose a REST endpoint for this checkout flow.

Throughout the process, I leveraged Git for version control, committing frequently as I completed prompt tasks. I also built in input validation and added test data.

To validate the implementation, I integrated with the existing Angular booking UI. I verified I could walk through the booking workflow end-to-end without errors, and confirmed the data was persisted correctly.

In summary, I successfully created a modern Spring microservice that mimics legacy booking functionality. This serves as an incrementally adoptable replacement for the outdated system. My work helped reduce risk for the customer by proving the viability of a migration.

------
### Glossary

Spring Framework - The modern Java framework chosen to replace the legacy back-end code. Promotes maintainability and reliability compared to old system.

Microservice - The new Spring back-end code is deployed as a standalone microservice, focused on specific booking workflow functions. Enables independent upgrades.

MVP - Minimum Viable Product. The initial simple "version one" of the new Spring microservice containing just enough functionality to showcase feasibility of the migration approach.

CRUD - Create, Read, Update, Delete. Basic data persistence operations exposed from the Spring back-end on booking entities like customers and vacation packages.

JPA/Hibernate - Java frameworks used by Spring for abstracting and simplifying database access, keeping entity code cleanly separated from SQL.

------

# Advanced Java

The goal was to enhance an existing Spring/Angular hotel booking application to support multiple languages and currencies per new management requirements.

I started by setting up Git version control and cloning the codebase. I then tackled the tasks of internationalizing the welcome message and prices displayed.

For localization, I created English and French resource bundles containing translated strings. I loaded these in different threads to demonstrate concurrent language support.

For internationalization, I updated the front-end to show US dollar, Canadian dollar and Euro prices. This prepares the app for global customers.

I also added time zone handling by writing a method to convert between Eastern, Mountain and UTC zones. I displayed a sample message with a hotel event time rendered in all three zones.

Towards deployability, I containerized the app using Docker. After testing locally, I described how I would deploy to a cloud provider - likely AWS Elastic Beanstalk to run the containerized workload.

Throughout, I focused on frequent commits associated with prompt tasks and left a README trail for my changes. I kept the revised code consistent with Angular/Spring best practices.

In summary, I successfully localized and internationalized this app by layering in language, currency, time zone and containerization support. This positions the product to be expanded globally in the future across new markets and geographies per the business needs.







