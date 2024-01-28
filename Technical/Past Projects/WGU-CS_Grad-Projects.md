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

**Database** - An organized collection of data stored and accessed electronically from a computer system.

**Table** - A set of data elements organized in rows and columns in a database.

**Field** - A column in a database table that contains a specific attribute for the rows.

**Query** - A request for data from a database table.

**Transform** - To convert or change data from one format or structure to another.

**Function** - A reusable block of SQL code that performs a specific task.

**Trigger** - A special stored procedure that runs automatically in response to an insert, update or delete event in a database table.

**Stored Procedure** - A reusable and executable SQL code block stored on the database server.

**Automate** - To configure systems or software to run recurring tasks automatically without manual intervention.

**Refresh** - To update data in a table or report with any new or changed information from the source.

**Scheduled Task** - A computer program action set to run automatically at a specified time interval.

**Reporting** - Creating views and visualizations that explain trends in business data.

**Dashboard** - A data visualization tool that displays key report metrics and data points on a single screen.

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

**Package Data** - Information associated with each package like delivery address, deadline, weight, status etc.

**Distance Matrix** - A table containing mileage between different location pairs. Helps calculate optimized routes.

**Interface** - The user-facing part of a software system for viewing data and accessing functionality.

**Real-time Tracking** - Displaying the current, up-to-date status and location of entities like vehicles or packages.

**Constraints** - Limits or conditions that solutions must satisfy, like maximum distance or delivery deadlines.

**Extensibility** - Designing software that is adaptable for enhancing functionality or scale in the future.

**Object Oriented Programming** - A programming paradigm based on objects that contain data and behaviors defined by class templates.

--------


