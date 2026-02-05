# b. Test Your Knowledge

Answer the following questions using VCAA terminology. Where appropriate, use full sentences and correct technical language.

---

## Question 1

Define a plain text (TXT) file.

??? note "Answer"
    A plain text (TXT) file contains characters of readable data and is read as character/string data types.

---

## Question 2

What is a delimiter in a delimited file?

??? note "Answer"
    A delimiter is a programmer-selected character used to separate values in a delimited file. Common delimiters include commas, tabs, and colons.

---

## Question 3

Explain the difference between CSV structure and XML structure. (2 marks)

??? note "Answer"
    **2 marks:** CSV uses delimiters (commas) to separate fields in a tabular row/column structure, with each line representing one record. XML uses tags to describe and separate data in a hierarchical tree structure with parent and child elements.

    **1 mark:** Partial explanation (e.g., mentions only one structure, or describes without comparing)

---

## Question 4

Describe one situation where a TXT file is more appropriate than CSV.

??? note "Answer"
    TXT is more appropriate for storing simple configuration settings (e.g., key=value pairs) where the data is unstructured and doesn't need to be organized into rows and columns. (Accept: small amounts of simple data that don't need delimiters or structure)

---

## Question 5

Describe one situation where CSV is more appropriate than XML.

??? note "Answer"
    CSV is more appropriate when storing tabular data with consistent fields across all records (e.g., student grades), because it has a smaller file size and is simpler to set up and program compared to XML. (Accept: when data needs to be easily transferred between spreadsheets and programs)

---

## Question 6

Describe one situation where XML is more appropriate than CSV.

??? note "Answer"
    XML is more appropriate when storing hierarchical or nested data where records may have a variable number of child elements (e.g., library books with multiple authors), because XML's tag-based structure can handle complex relationships that CSV's flat row/column structure cannot. (Accept: when data structure needs to be flexible/extensible)

---

## Question 7

A program stores a list of students, each with: Name, House, YearLevel.

Which file type (TXT/CSV/XML) would you choose and why? (3 marks)

??? note "Answer"
    **3 marks - Full response with comparison:**

    CSV would be most appropriate. The data is tabular with consistent fields (Name, House, YearLevel) across all student records. CSV uses delimiters to separate these fields, making it easy to process as rows and columns. CSV is simpler to implement and has a smaller file size than XML, which would be unnecessarily complex for this flat data structure. TXT would not be suitable because it lacks clear field separation.

    **2 marks:** Correct choice with structure and one reason, but no comparison

    **1 mark:** Correct choice with basic reasoning

    **Key elements for full marks:**
    - Identifies CSV as most appropriate
    - Describes CSV structure (delimiter-separated fields, tabular)
    - Explains why it suits this scenario (consistent fields, simple structure)
    - Compares to other formats (XML too complex, TXT lacks structure)

---

## Additional Practice Questions

### Question 8

State one advantage of CSV over XML.

??? note "Answer"
    Smaller file size, making transmission faster. (Accept: Simpler to set up and program)

---

### Question 9

State one advantage of XML over CSV.

??? note "Answer"
    XML is extensible and can accommodate structural changes. (Accept: Can handle nested/hierarchical data; Self-describing with tags; Can handle commas/line breaks in data without breaking structure)

---

### Question 10

What is the purpose of a prolog in an XML file?

??? note "Answer"
    The prolog declares that the file is XML and specifies details such as the XML version and character encoding. (Accept: Provides metadata about the XML document)

---

!!! tip "Exam Success"
    When comparing file formats:

    1. **Describe the structure** of each format first
    2. **Explain why** one is better for the specific scenario
    3. Always **compare**, don't just describe one option
    4. Use specific terminology: delimiters, tags, hierarchical, tabular, nested
