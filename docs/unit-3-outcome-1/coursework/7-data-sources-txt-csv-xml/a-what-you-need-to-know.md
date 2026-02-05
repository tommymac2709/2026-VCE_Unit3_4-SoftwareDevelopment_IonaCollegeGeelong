# a. What You Need To Know

!!! info "Key Knowledge - KK 3.1.6"
    Characteristics of data sources (plain text (TXT), delimited (CSV) and XML files), including:

    - Structure
    - Reasons for use

---

Files let a program save information to be retrieved later, which is why they are used in many software solutions.

## Text files vs binary files

!!! tip "Key Point"
    **Text files** store data as readable plain text

    **Binary files** store data in binary form (e.g. images/sound) and are not easily readable

In Software Development, you focus on text files.

---

## Plain text (TXT) files

### Structure

!!! tip "Key Point"
    A plain text (TXT) file contains characters of readable data and is read as character/string data types.

In practice, it's usually:

- One value per line, or
- A simple pattern (e.g. key=value)

### Reasons for use

TXT files are commonly used for:

- configuration settings
- storing small amounts of data in simple programs

!!! info "Note"
    Even though they can be opened by humans, they're typically designed for fast processing by programs, so they often lack headings/comments that help humans.

---

## Delimited files (CSV)

### Structure

!!! tip "Key Point"
    A delimited file stores values separated by a programmer-selected character called a **delimiter**. Common delimiters include commas, tabs and colons.

    If the delimiter is a comma → it's a **CSV (comma-separated values)** file

Delimited files allow storage of two-dimensional arrays in a structured, readable format (rows/columns).

### Reasons for use

**CSV is useful when:**

- Data is tabular (rows/columns)
- You want a simple format that is easy to move between tools (e.g. spreadsheets ↔ programs)
- Data structure is consistent (same fields each row)

!!! info "Examiner-style advantages"
    Examiner-style advantages commonly credited include:

    - Smaller file size → faster transmission
    - Easier to set up and program

---

## XML files

### Structure

!!! tip "Key Point"
    XML uses tags to describe and separate data, and is structured like a tree:

    - a root element
    - parent elements
    - child elements

XML may also include a **prolog** (before the document contents) containing details like XML version and character encoding.

### Reasons for use

**XML is useful when:**

- Data is hierarchical (nested)
- You need self-describing data (tags explain what fields mean)
- You expect the structure might evolve (more flexible than strict row/column)

!!! info "Examiner-style advantages"
    Examiner-style advantages commonly credited include:

    - Extensible (can accommodate structural changes)
    - Often easier for humans and computers to read
    - Can handle commas/line breaks without breaking field meaning (compared to naive CSV parsing)

---

## CSV vs XML (the comparison you must be able to write)

!!! warning "Important"
    A high-scoring comparison typically:

    - describes **how each is structured**, and
    - explains **why one is better for the scenario** (not just "XML is better")

**Examiners reward explicit structure statements like:**

- CSV uses delimiters to separate fields
- XML uses tags that describe what each field contains
