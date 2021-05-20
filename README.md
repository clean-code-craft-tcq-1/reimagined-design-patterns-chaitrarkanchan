# reimagined-design-patterns

Give a summary description of Four design patterns that you choose from the following design patterns: **Adapter,  Builder, Composite, Decorator, Observer, Interpreter, State, Mediator, Memento, Prototype, Proxy**. In your summaries say:

- what kind of problem(s) you can solve with that pattern and when you use it, maybe with a short example
- how the pattern works, what the basic idea of the pattern is
- what the main advantage and what the the main disadvantage is of using this pattern
- Write a short summary for each of the four patterns, about half a page for each pattern (rather less than more). 

> Do not add diagrams, and do not try to give a complete description of the patterns as found in the books. Rather think of how you would explain the essential ideas of these patterns in a few sentences to a colleague while drinking coffee.

## Adapter Pattern
This pattern allows incompatible classes to interact with each other by converting the interface of one class into an interface expected by the clients.
Consider a service which returns weather (in Celsius) by passing city name as a input value. Now, assume that your client wants to pass zip code as input and expecting the temperature of the city in return. This can achieve using adapter Pattern this.

The client sees only the target interface and not the adapter. The adapter implements the target interface by reusing several existing subclasses that lack some common functionality that can’t be added to the superclass. Adapter delegates all requests to Adaptee.

**Advantages:**

•	It supports Open Closed principle where you can introduce new types of adapters into the program without breaking the existing client code, as long as they work with the adapters through the client interface

**Disadvantages:**

•	It increases the complexity of the code, as number of interfaces and classes grows.

## Builder Pattern
 It is a creational design pattern , a Builder class builds the final object step by step. The Builder pattern suggests that you extract the object construction code out of its own class and move it to separate objects called builders. The pattern organizes object construction into a set of steps. To create an object, you execute a series of these steps on a builder object. The important part is that you don’t need to call all of the steps. You can call only those steps that are necessary for producing a particular configuration of an object.
 
 For example, let’s think about how to create a Pizza object. To make pizza based on the type of toppings, sauce and size it differs. Based on type of pizza specific topping, sauce and size need to be added.
 
 **Advantages:**
 
 - Solves the issue with large number of optional parameters and inconsistent state by providing a way to build the object step-by-step and provide a method that will actually return the final object.
 - Provides control over steps of creation process.
 - Different representation of object is possible.

**Disadvantages:**

- The builder pattern is verbose and requires code duplication as Builder needs to copy all fields from Original/Outer Class.
- Data members of class aren’t guaranteed to be initialized.
- Dependency injection may be less supported.

## State Pattern: 
State is a behavioral design pattern that lets an object alter its behavior when it’s internal state changes. In state pattern, we can create objects which represent various states and a context object whose behavior varies as its state changes.
Consider an ATM machine, if the state is Debit Card Not Inserted then it will allow you to perform certain operations and when the state is Debit Card Inserted then it will allow you to perform another set of operations. So, based on the internal state of the ATM machine the behavior will be changed

**Advantages:**
- Reduces the complexity by eliminating the state conditional statements.
- Behavior is determined at run time, and can easily change.
- It can easily be extended, i.e. new behavior can easily be added.

**Disadvantages:**

- If there are multiple states, we need a class for each state and the overall program can easily become too complex. But this also provides a separation of concern so it is also an advantage.
- The memory use can be too high, if there are many objects, each one with its own state. This can easily be avoided by making the states singleton objects.

## Proxy Pattern:
Proxy is a structural design pattern that lets you provide a substitute or placeholder for another object. A proxy controls access to the original object, allowing you to perform something either before or after the request gets through to the original object.
Example consider college internet or any office internet, which restricts few site access. The proxy first checks the host you are connecting to, if it is not part of restricted site list, then it connects to the real internet.

**Advantages:**
- One of the advantages of Proxy pattern is security.
- This pattern avoids duplication of objects which might be huge size and memory intensive. This in turn increases the performance of the application.
- The remote proxy also ensures about security by installing the local code proxy (stub) in the client machine and then accessing the server with help of the remote code.

**Disadvantages:**

•	This pattern introduces another layer of abstraction which sometimes may be an issue if the RealSubject code is accessed by some of the clients directly and some of them might access the Proxy classes. This might cause disparate behaviour.
