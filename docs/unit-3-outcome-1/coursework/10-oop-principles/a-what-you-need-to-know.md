# What You Need To Know

!!! abstract "Learning Objectives"
    Understand the four fundamental principles of Object-Oriented Programming.

---

Object-oriented programming (OOP) is a programming paradigm that organises software using objects, which combine data and behaviour.

The following principles are used to design clear, reusable and maintainable object-oriented solutions.

## Abstraction

!!! tip "Definition"
    Abstraction is the process of:

    - identifying the essential features of an object
    - ignoring unnecessary or irrelevant details

Abstraction focuses on:

- **what** an object does
- **not how** it does it

This allows developers to model real-world entities in a simplified way that is appropriate for the problem being solved.

!!! info "Key textbook emphasis"
    - Only relevant attributes and behaviours are included
    - Unnecessary complexity is hidden
    - Different problems may require different abstractions of the same real-world object

!!! warning "📌 Exam language"
    Abstraction reduces complexity by focusing on relevant features only.

---

## Encapsulation

!!! tip "Definition"
    Encapsulation is the principle of:

    - bundling data (attributes) and methods (behaviour) together within a class
    - restricting direct access to the data

Encapsulation:

- protects data from unintended modification
- improves reliability
- ensures that data is only accessed or changed in controlled ways

This is commonly achieved by:

- keeping attributes **private**
- providing **public** methods to interact with the data

!!! info "Key textbook emphasis"
    - Data should not be directly accessible from outside the class
    - Methods act as the interface to the object's data

!!! warning "📌 Exam language"
    Encapsulation improves data security and program reliability.

---

## Generalisation

!!! tip "Definition"
    Generalisation is the process of:

    - identifying common attributes and behaviours shared by multiple classes
    - creating a more general class that represents these shared features

The general class:

- represents what the specialised classes have in common
- reduces duplication of code
- improves maintainability

!!! info "Key textbook emphasis"
    - Generalisation is used when multiple objects share similarities
    - It supports code reuse by avoiding repeated definitions

!!! warning "📌 Exam language"
    Generalisation reduces repetition by grouping common features into a single class.

---

## Inheritance

!!! tip "Definition"
    Inheritance allows a class to:

    - be created from another class
    - automatically acquire the attributes and methods of the more general class

The original class is often referred to as the:

- **general** (parent/base) class

The new class is referred to as the:

- **specialised** (child/derived) class

Inheritance represents an **"is-a"** relationship.

!!! info "Key textbook emphasis"
    - Specialised classes can add new features
    - Specialised classes reuse existing functionality
    - Inheritance is built on generalisation

!!! warning "📌 Exam language"
    Inheritance supports reuse by allowing specialised classes to inherit common features.

---

## Relationship between the principles (textbook framing)

The textbook presents these principles as linked, not isolated:

- **Abstraction** → decide what features matter
- **Encapsulation** → protect and control those features
- **Generalisation** → identify common features across classes
- **Inheritance** → reuse those features in specialised classes

---

## 40+ Exam reminders

!!! danger "Critical Points"
    - Abstraction is about **relevance**, not hiding code
    - Encapsulation is about **data protection**, not just grouping code
    - Generalisation comes **before** inheritance
    - Inheritance describes an **is-a** relationship, not a has-a relationship
    - Always explain **why** the principle is used
