# a. What You Need To Know

Data types define how data is stored and processed by a program.

Every variable declaration includes a type so that the computer knows the amount of memory to reserve and the operations allowed.

| Data type | Description | Example value |
| --- | --- | --- |
| String | Sequence of characters | "Alice" |
| Integer / Long | Whole numbers | 42 |
| Float / Double / Decimal | Decimal numbers | 3.14 |
| Boolean | True / False values | True |
| Character | Single symbol | 'A' |

Data structures organise multiple data items so they can be efficiently accessed or manipulated.

| Structure | Description | Example use |
| --- | --- | --- |
| Array / List | Ordered collection, indexed numerically | Store 10 test scores |
| Dictionary / Map | Key-value pairs | Store studentID → score |
| Record / Class | Group of fields of possibly different types | Customer (name, ID, balance) |
| Stack / Queue | Abstract structures controlling access order | Undo stack; print queue |

## Data Types (KK3.1.4)

In programming, a data type is a method of classifying a variable to determine the data that variable can contain, as well as how the variable can be manipulated – that is, what it can do, and what can be done to it. While programming languages vary widely from each other, data types do not; they are consistent across all programming languages. When programming, it can be important to choose an appropriate data type when creating a variable. It is also important to select the most efficient data type. For example, it is not efficient to select a numeric data type that supports decimal places when creating a variable if that variable will only ever contain whole numbers. Similarly, storing a number as a string is not as efficient as storing it as a numeric data type, even if it is possible to convert strings to numbers.

Numeric – The numeric data type consists of whole numbers, referred to as integers; decimal numbers, referred to as floating points; and date/time, which are stored in integer form. Integers can be referred to as unsigned, which means they can only store positive whole numbers, or signed, which means they can store both positive and negative whole numbers. All numeric data types can have mathematical operations performed on them, including addition (+), subtraction (–), multiplication (*), division (/), whole number division (//), remainder after division (%), powers (**), and assignment (= or ←). Numeric data can also undergo comparisons such as <, ≤, >, ≥, ==, and !=.

Text – Both text and characters can undergo the same comparisons as numeric data types, and depending on the programming language, can also use fundamental data type operations such as addition, multiplication and assignment. An example of text addition is:

```
INPUT firstName
PRINT “Hello “ + firstName + “!”
```

Boolean – Boolean data types have only two possible values: 0 and 1. In a programming language these are often referenced with the words ‘False’ or ‘True’. This data type is named after George Boole, a 19th-century mathematician who defined an algebraic system of logic. Boolean data types are very useful for systems that require decisions to be made or conditions to be met. Boolean values can be used with logical operators and, or, and not, in statements where a condition must be met, such as:

```
IF isDark = True AND lightOn = False THEN
    turnOnLight()
ENDIF
```

## Data Structures (KK3.1.5)
A data structure is a method of organising data to allow particular operations to be performed on them efficiently; in this way, data structures are more complex than data types. The types of data structures used in Software Development are: one-dimensional arrays, two-dimensional arrays, and records.

Array – An array is a data structure that contains groupings of data. These elements must be of the same data type, such as character, numeric or Boolean. Arrays can also store groupings of other data structures, such as fields, records or even other arrays. The contents of an array are referenced using an index value – often an integer starting at 0. Arrays can be considered to have dimensions. A one-dimensional array is a linear data structure where elements are accessed by a single index. A two-dimensional array stores elements in a grid-like format, organised into rows and columns, allowing access using two indices.

Record – Records are collections of related data (fields) that may or may not have the same data types.

Summary Facts – Data structures are more complex than data types. Arrays start at index value 0 in almost all programming languages. Arrays traditionally contain elements of the same data type, but this depends on the programming language selected.
