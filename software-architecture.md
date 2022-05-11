# Software Architecture

Time to think of robotics from a software architect's perspective.

We need to design a software for the application of controlling robotic systems autonomously.

## Motivation

- Better reason on what the architecture is supposed to do.
    - Abstraction of code lets us say “this module does this”.
    - More obvious as to what each element does.
- Better maintain the architecture.
    - Dependencies are better understood.
    - Architectures aim to have low-coupling => making changes will be easier. 
- Easier to extend the architecture.
    - Extensions are possible through clearer understanding of relationships between elements.
- Reusability of some element of the architecture.
    - Saves time and energy rather than design from scratch.
- Easier to foresee/dictate implementation.
    - Architecture is the skeleton to writing code.
    - Interface is defined.
- Easier to communicate.
    - Clients will better understand higher-level abstractions.
    - Saves you time talking to peers.

## Anatomy

An architecture consists of:
- Element: Some level of encapsulation of some information.
- Relationship: How information flows between elements.

## Architectural Principles

A rule that we follow to ensure good design practices.

### Policy vs Detail

- Policy: Defines rules and interfaces.
- Detail: Concerned with implementation details i.e. specifies how a policy is achieved.

> It is important to realise that the designer dictates how the software will be implemented.

### Coupling vs Cohesion

- Coupling: Dependency of elements on each other.
- Cohesion: Grouping of similar elements together.

We aim for low coupling but high cohesion.

### Stable Abstraction Principle

The more stable an element is, the more abstract it should be.

> Why? Because we don’t want to change the interface of this element.

### Stable Dependency Principle

More stable elements should never depend on less stable elements. This keeps points of failure in the system isolated to less stable elements and be confident that the more stable elements are indeed stable.

> It doesn’t propagate failure/risk throughout the system.

### Acyclic Dependency Principle

Architecture should not have any elements depending on each other to form a cycle.

## Architectural Styles

A particular way we design our architecture. The style of architecture is used to best represent what the architecture does.

### Structural

Hierarchical representation is important.

Examples:
- Component-Based
- Monolithic
- Layered

### Messaging

Information-passing representation is important.

Examples:
- Event-Driven
- Publish-Subscribe

### Distributed

Platform-requirements representation is important.

Examples:
- Client-Server
- Peer-to-Peer

## Architectural Patterns

A derivation of principles and styles used to solve common problems.

### Entity-Component-System

### Master-Slave

### Blackboard

## Robotic Software Architecture

What systems and subsystems do we need? How abstract and coupled should they be?

We could have a localisation package and a separate mapping package. We could combine the two together to have a SLAM package.

Consider:
- Hardware constraints.
- Available tools/libraries.
- Effort and time.
- Maintainability.
- Scalability.

### Control Loops

One important thing to realise about robotic software is that it is one big while loop which we call the control loop. The typical control loop will implement the see-think-act cycle.

```python
while true:
    isDetected = detectRoad()
    if isDetected is True:
        driveForward()
```