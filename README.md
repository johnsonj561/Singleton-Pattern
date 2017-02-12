----------------------------------------------------------------------------------------------------------------
Title: The Singleton Pattern

Sources:
Notes below regarding composite pattern taken from "Design Patterns - Elements of Reusable Object-Oriented Software"
By Gamma, Helm, Johnson, Vlissides

Example Code provided by Derek Banas:
Tutorial: https://www.youtube.com/watch?v=NZaXM67fxbs
Source Code: http://www.newthinktank.com/2012/09/singleton-design-pattern-tutorial/

Author: Justin J

Purpose: FAU Object Oriented Software Design Course, Sprint 2017

----------------------------------------------------------------------------------------------------------------

Intent
- to ensure a class has only 1 instance and provide a global point of access to it

Motivation
- it is important for some classes to have only 1 instance
	- ex) printer spooler, file system, window manager, etc
- force the class to keep track of its sole instance

Applicability
- to be used when there must be exactly one instance of a class and it must be accessible to clients
- when sole instance should be extensible by subclassing, and clients should be able to use an extended instance
  without modifying their code
  
Structure
- see singletondiagram.di

Participants
- Singleton
	- defines a static instance operation that lets clients access its unique instance
	- may be responsible for creating its own unique instance if does not already exist

Collaborations
- clients access singleton instance through it's static instance operation

Consequences
- Controlled access to sole instance
	- it encapsulates its sole instance, it can have strict control over how and when clients access it
- Reduced name space
	- improvement over global variables. It avoids polluting the name space with global variables that store
	  sole instances
	  
Implementation
- Ensuring a unique instance
	- class is written so that only one instance can ever be created
	- accomplished with a static method that has access to the unique instance and ensures that the instance
	  has been initialized. 
- Subclassing the Singleton class
	- issue is installing unique instance to subclass so clients will be able to use it
	- the variable that refers to the singleton instnace must get initialized with an instance of the subclass
	- flexible approach is to use registry of singletons. Singleton classes can register their singleton instance
	  by name in a well known registry
 
Related Patterns
- Abstract Factory, Builder, and Prototype
 

          	