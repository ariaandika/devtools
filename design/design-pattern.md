# Design Pattern

Design pattern is a pattern that can be used inside a codebase, where we follow a convention to create a predictable design.

## Creational Pattern

Rule how object are created

### Factory

Pattern where we create an instance with one method. We only need to tell what kind of instance we needed. With this, we hide all what inside the instance.

Example is where we want a cross platform button. We can just call createButton and the logic inside the function will check the underlying platform.

### Builder

Pattern where we chain a method to create an instance. With this, we know exactly what needed to create the instance.

### Singleton

Pattern where there will be only one instance at any time. We use static method to set the properties of its instance. This usually use in shared properties like settings.

### Prototype

Create an object based on multiple tiny object that not even created. This same concept as interface in oop, or trait in rust.

## Structural Pattern

Rule how object relate to each other

### Adapter

Where a function that make a value compatible to an input. The real world example of this is where a microusb cable cannot fit into usb port. We create a microusb adapter where we can input a microusb cable, then input it into the usb port.

### Facade

Facade hide the complex structure of lower level detail as simple interface. Example of this is fetch api, where it hide the complexity of tcpstream as single function.

### Proxy

A function where we can intercept a value before it can be sended to the target. Example, whenever we change a value, a proxy will update the correponding ui to display the updated data.

## Behavioral Pattern

Rule how object communicate with each other

### Observer

Where an instance subscribe to publisher instance as source of events. When publisher instance call an event, all subscriber instance get notified to call its corresponding function. This is usually used for realtime data transfer.

### Iterator

An object where it can be iterated. This can be an array that iterated from one element to the next, or a linked list where we iterate from one object to other object. Other than that, we can create an object lazily, by provide function as iterator.

### Strategy

A system where we can create a family of algorithms or strategies, encapsulate them as an object, and make them interchangeable at runtime.

Example of this is, where a car can be driven manually or automatically. If the road is simple and easy to navigate, we can use autodrive strategy. But when the road have more turn and it in the hills, we cannot trust autodrive and switch to manual driving strategy.

### Mediator

Centralize how object communicate. A many to many relationship is to dangerous. Instead, we can create an instance to intercept this communication and redirect them properly.

This is simmilar how middleware works. Example, before we let the user access a data, we intercept the request for authentication. If it pass, we allow the request to reach specific endpoint.

### State

We create an object, where we can input as a state. By following some rule, we can create as many state as we want, without changing the main state manager logic.
