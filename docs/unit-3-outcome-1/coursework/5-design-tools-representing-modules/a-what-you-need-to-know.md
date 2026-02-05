# a. What You Need To Know

## Design Tools for Representing Modules

Once a software requirements specification has been completed, considerable time should be spent designing the software that is going to be written, as problems are normally resolved before any code has been written. Some common methods of representing designs are data dictionaries, object descriptions, mock-ups, IPO charts, and pseudocode, each serving a different purpose in the design stage.

!!! tip "Key Point"
    Design tools help resolve problems **before any code has been written**, saving time and effort during development.

---

## Data Dictionaries

A data dictionary is used to plan the storage of software elements, including variables, data structures, and objects such as GUI text boxes or radio buttons. It lists every variable's name and data type or structure and may also include the data's purpose, source, size, description, formatting and validation.

They are valuable when code needs to be modified later by other programmers and the purpose of a variable is unclear.

### Example

| Name | Type | Format | Purpose |
| --- | --- | --- | --- |
| customerId | integer | 999999 | Unique identifier for a customer |
| postCode | string | 9999 | Postcode for a suburb |
| userActive | Boolean | True/False | Stores if user is active or not |
| totalOrderCost | floating point | 99.99 | Total cost of an order |

!!! tip "Key Point"
    Data dictionaries are valuable when **code needs to be modified later** by other programmers and the purpose of a variable is unclear.

---

## Object Descriptions

An object description details all relevant properties, methods, and events of an object.

### Steps to create one:

1. Identify the object.
2. Define its attributes.
3. Define its methods.
4. Combine attributes and methods into a comprehensive description.

These are valuable when code needs modification and the properties of objects are unclear.

---

## Mock-ups

Mock-ups are sketches showing how an interface screen or printout will look, ensuring that the program is usable and clear. They typically include:

- positions and sizes of controls (buttons, scroll bars),
- positions, sizes, colours and styles of text (headings, labels),
- menus, status bars, frames, shapes, colours and alignment.

A mock-up is successful if another person can create the interface without needing clarification.

!!! info "Success Criteria"
    A mock-up is successful if **another person can create the interface without needing clarification**.

---

## IPO (Input–Process–Output) Charts

IPO charts conceptualise how data moves through a program. They identify what data is received (input), what happens to it (process), and what is produced (output).

### Example

| Input | Process | Output |
| --- | --- | --- |
| Original Price, Discount % | Calculate discount (Original Price × Discount %) and subtract from price | Final Price |

---

## Pseudocode

Pseudocode represents algorithms using structured English that is independent of any programming language. It is designed to describe logic and sequence without syntax requirements.

!!! tip "Key Point"
    Pseudocode is **independent of any programming language** - it describes logic without syntax requirements.

---

## Summary

Design tools such as data dictionaries, object descriptions, mock-ups, IPO charts, and pseudocode provide structured ways to plan, communicate, and document the design of software before coding begins, helping developers ensure clarity, maintainability, and usability.
