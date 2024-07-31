# Object-Oriented-Analysis-Design-Review-12

## Deploying the New System

### 6-Phase SDLC index

1. Identify problem
2. Plan and monitor project
3. Analyze details
4. Design components
5. Build / Develop solution
6. **Deploy / Implement solution**

-----

### Testing
| Test type                 | Core process   | Need and purpose                                                                                                                                                                                                                 |
|-------------------------- |----------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Unit testing              | Implementation | Software components must perform to the defined requirements and specifications when tested in isolation                               |
|                           |                | For example, a component that incorrectly calculates sales tax amounts in different locations is unacceptable.                         |
| Integration testing       | Implementation | Software components that perform correctly in isolation must also perform correctly when executed in combination with other components |
|                           |                | They must communicate correctly with other components in the system.                                                                   |
|                           |                | For example a sales tax component that calculates incorrectly when receiving money amounts in foreign currencies is unacceptable.      |
| System and stress testing | Deployment     | A system or subsystem must meet both functional and non-functional requirements.                                                       |
|                           |                | For example an item lookup function in a Sales subsystems retrieves data within 2 seconds when running in isolation                    |
|                           |                | But requires 30 seconds when running within the complete system with a live database.                                                  |
| User acceptance testing   | Deployment     | Software must not only operate correctly.                                                                                              |
|                           |                | But must also satisfy the business need and meet all user “ease of use” and “completeness” requirements                                |
|                           |                | For example, a commission system that fails to handle special promotions function with a poorly designed sequence is unacceptable.     |

#### Unit-Testing - Driver and stub components
- (Driver)---[ ]---(Stub)(Stub)
**Driver**
- A method or class developed simulates the behavior of a method
- Sends a message to the method being tested
**Stub**
- A method or class developed for unit testing
- Simulates the behavior of a method invoked that hasn’t yet been written

#### Integration Testing
Tests of the behavior of a group of methods, classes, or components.

**Test Interface incompatibility**
- See if a method passes a parameter of wrong data type to another method 

**Test Parameter values**
- Methods can be (and usually are) called by many other methods
- The calling methods may be distributed across many classes

**Test Run-time exceptions**
- A method generates an error like “out of memory” or “file already in use” due to conflicting resource needs

**Test Unexpected state interactions**
- The states of two or more objects interact to cause complex failures
- When an OnlineCart class method operates correctly for all possible Customer object states except one

##### Integration Testing Procedures
1. Build unit test the components to be integrated
2. Create test data
3. Conduct the integration test
4. Evaluate the test results
5. Log the test results
6. Correct the code and retest

#### System, Performance & Stress Testing
**System test**: An integration test of an entire system or independent subsystem
**Performance test**: Look for peak throughput / computing speed / Response time 
**Stress test**: Look for stability under heavy and consistent load

#### Use Acceptance Testing (UAT)
Determine whether the system fulfills user requirements
- May be performed near the end of the project
- May be at end of later project iterations
- A very formal activity in most development projects.
- Payments tied to passing tests

Details of acceptance tests are sometimes included in:
- Request for proposal (RFP)
- Procurement contract

##### Plan the Use Acceptance Testing
- Should be done early in the project 
- Test cases for every use case and user stories
- Identify conditions to verify that the system supports the use case accurately and completely

Preparation and Pre-UAT Activities
- Develop test data – data entry and database records
- Plan and schedule specific tests
- Set up test environment

**Usability Testing**
- Checks the User Friendliness, user interface, and user satisfaction when using the system

**Manage and execute the UAT**
- Much like a mini-project
- Assign responsibilities
- Document and track results 

-----

### Deployment Activities

#### Converting and Initializing Data 
An operational system requires a fully populated database

Data needed at system startup can be obtained from these sources:
- Files or databases of a system being replaced
- Manual records
- Files or databases from other systems in the organization
- User feedback during normal system operation

**Reuse existing database**
- Modify or update existing data

**Reload databases**
- Copy and convert the data
- Export and import data from distinct D B M Ss
- Data entry from paper documents

**Complex data conversion example**:
(Old DB)-->[Copy & Convert Data]-->(New DB)
(Old DB)-->[DBMS Import Utility]-->(New DB)
(Related subsystem DB)-->[DBMS Export Utility]-->(Temporary Data Store)-->[DBMS Import Utility]-->(New DB)
{Paper Records}-->[Manual Input]-->(New DB)

#### Training Users
Training is needed for end users and system operators

**Must emphasize**
- Hands-on use for specific business processes or functions:
  - i.e., order entry, inventory control, or accounting
- Widely varying skill and experience levels:
  - Require training including practices, questions & answers, tutorials
- System operator training can be much less formal when the operators aren’t end users
- Experienced computer operators and administrators can learn most or all they need to know by self-study

| End-user activities              | System operator activities       |
|----------------------------------|-------------------------------- -|
| Creating records or transactions | Starting or stopping the system  |
| Modifying database contents      | Querying system status           |
| Generating reports               | Backup up data to archive        |
| Querying database                | Recovering data from archive     |
| Import or exporting data         | Installing or upgrading software |

### Planning and Managing Implementation, Testing, and Deployment

#### Development Order
**Input, process, output (IPO)**
- A development order that implements input modules first
- Process modules next, and output modules last 

**Top-down development**
- A development order that implements top-level modules first
- Use stubs for testing

**Bottom-up development**
- A development order that implements low-level detailed modules first
- Use drivers for testing

**Use-case driven**
- Select specific use cases and order the development based on selected use cases

#### Source code control
An automated tool for tracking source code files and controlling changes to those files
- A programmer checks out a file in read-only mode when:
  - He/she wants to examine the code
  - Without making changes (e.g., to examine a module’s interfaces to other modules)
- When a programmer needs to make changes to a file, he or she checks out the file in read/write mode
- The SCCS allows only one programmer at a time to check out a file in read/write mode.

#### Packaging, installing, and deploying components
- Issues to consider when planning
- Incurring costs of operating both systems in parallel
- Detecting and correcting errors in the new system
- Potentially disrupting the company and its IS operations
- Training personnel and familiarizing customers with new procedures

#### Different approaches
- Direct deployment
- Parallel deployment
- Phased deployment

##### Direct deployment**
A deployment method that:
- Installs a new system
- Quickly makes it operational
- Immediately turns off any overlapping systems

**Parallel deployment**
A deployment method that:
- Operates the old and the new systems for an extended time period

**Parallel deployment problems**
- Incompatible inputs (old and new)
- Heavier load on equipment, may not have sufficient capacity for both
- Heavier load on staff, may require overtime

**Partial parallel may be an option**
- Process only a subset of the data
- Use only part of the system – only some functions

##### Phased deployment
A deployment method that installs a new system and makes it operational in phases

**Change and Version Control**
- Tools and processes handle the complexity associated with testing
- Supporting a system through multiple versions

**Alpha version**
- A test version that is incomplete but ready for some level of rigorous integration or usability testing

**Beta version**
- A test version that is stable enough to be tested by end users over an extended period of time
- Production version, release version, or production release

**Maintenance release**
- A system update that provides bug fixes and small changes to existing features

-----

### Quiz

​A Web based application that integrates HTML code with business logic is said to be in violation of what design principle?
- Protection from variations

​An object-oriented program consists of a set of object classes that work together to process an input message.
- False

Which of the following is true of class-level methods?
- They are executed by the class instead of a specific object of the class.

​The only difference between a domain class diagram and a design class diagram is the addition of the methods.
- False

​Visibility is a design property that indicates whether a class can be “seen” by the user interface classes.
- False

Which of the following is included in the top compartment of a design class?
- Stereotype name

CRC stands for Class-Responsibility-Communication.
- False, Class-Responsibility-Collaboration

​The objective of object-oriented analysis is to identify the objects that must work together to carry out each use case.
- True

​If you are doing detailed design for the use case Create New Order, which class should receive the first input?
- Order Handler

A class named SaleItem which has methods to calculate its own price is said to have good ______.
- Object responsibility

Which of the following is correct UML notation for an attribute in a design class?
- visibility name:type-expression = initial-value{property}

If you are doing detailed design for the use case Create New Order, which class should receive the first input?
- Order Handler

____ is a qualitative measure of the consistency of functions within a single class.
- Cohesion

Given two classes, customer and order, which class would probably have navigational visibility to which class?
- Customer to Order

Which of the following is usually NOT included in a first-cut design class diagram?
- Method signatures

Which diagram is directly used to identify methods and write programming code for object-oriented systems?
- Design class diagram

Which is a valid sequence of modeling steps for designing a use case?
- First cut DCD, Communication diagram, Final DCD, Package Diagram

A Web based application that integrates HTML code with business logic is said to be in violation of what design principle?
- Protection from variations

Which of the following is included in the top compartment of a design class?
- Stereotype name

A class that is responsible for accessing both the Internet and a database has ____ cohesion.
- Very low

Which of the following is NOT part of a multilayer object-oriented design (OOD)?
- Functional module

Which of the following is NOT one of the design models used for object-oriented design.
- System sequence diagram

Which of the following is valid Unified Modeling Language (UML) notation for a method signature?
- Visibility name(parameter list):type-expression

If a class is reusable, that is to say that it can be used in several different applications, then it has been designed using what good design principle? An example might be a button class.
- High cohesion

Which of the following is the best coupling choice for an input window, domain, and database object in a system?
- The input window is coupled to the domain and the domain is coupled to the database.

In a design class diagram, navigation visibility is identified by ____.
- A solid arrow between the classes, pointing to the visible class

Which analysis model serves as an input model to a design class diagram?
- Domain model class diagram

High coupling adds ____ in a system.
- Complexity

Which of the following is a general guideline for designing navigation visibility?
- A superior/subordinate relationship is usually navigated from the superior to the subordinate class

Which two models are primary models in object-oriented detailed design?
- Sequence diagram and design class diagram

A(n) ____ class acts as a switchboard between the view layer and the domain layer.
- Controller

After completing a use-case design using CRC cards, the next step is to _______.
- Update the design class diagram

An input window class is an example of a(n) ____ design class type.
- Boundary

UML provides a technique to extend the standard UML notation to include new symbols. This technique is called ________.
- Stereotyping

In Unified Modeling Language (UML) notation, a stereotype is indicated by ____.
- Guillemets

In design class notation, the ____ of an attribute is enclosed in curly braces {}.
property
Which of the following is true of class-level methods?
- They are executed by the class instead of a specific object of the class.

A plugin, such as adobe PDF reader, that is attached to a browser, such as Firefox, is a good example of what design principle?
- Separation of concerns

Which of the following is the best coupling choice for an input window, domain, and database object in a system?
- The input window is coupled to the domain and the domain is coupled to the database.

When a use case controller receives the initial request for an inquiry when the data access layer is added, it first ____.
- Begins the process to initialize the necessary data access objects in memory

According to an Agile iterative development process in which iteration would implementation activities normally start?​
- ​First iteration

Adding a use case controller to a sequence diagram is an example of applying a design pattern
- True

The objective of design activities is to describe in detail the components of the final solution system that will serve as a blue print for construction
- True

In generalization/specialization the attributes(but not the associations) of the subclass are inherited from the superclass
- False

Designing a single user interface is now the exception, not the norm
- True
