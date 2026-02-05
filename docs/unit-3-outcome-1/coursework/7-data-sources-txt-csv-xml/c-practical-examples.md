# c. Practical Examples

---

## Example 1 — TXT (simple settings)

**Scenario:** A game needs to store user preferences that are loaded each time the program runs.

**File: settings.txt**

```
theme=dark
fontSize=14
musicOn=true
username=PlayerOne
difficulty=medium
volume=75
```

**Structure breakdown:**

- Each line contains one configuration setting
- Uses `key=value` pattern for easy parsing
- No headers or delimiters needed
- Simple string processing to read each line

**Why TXT works:** Small amount of simple data, easy to read/write quickly.

**Reading this in C#:**

```csharp
// Read all lines from TXT file
string[] lines = File.ReadAllLines("settings.txt");

// Process each line
foreach (string line in lines)
{
    // Split on '=' to get key and value
    string[] parts = line.Split('=');
    string key = parts[0];      // e.g., "theme"
    string value = parts[1];    // e.g., "dark"

    Console.WriteLine($"{key}: {value}");
}
```

!!! tip "When to use TXT"
    - Configuration files with simple key=value pairs
    - Small amounts of unstructured data
    - Single values per line
    - Quick and simple to implement

---

## Example 2 — CSV (tabular data / 2D array)

**Scenario:** A school needs to store student records in a format that can be opened in Excel and processed by a program.

**File: students.csv**

```
StudentID,FirstName,LastName,Score,Grade,House
1023,Aisha,Khan,87,A,Kendall
1024,Luca,Rossi,91,A,O'Brien
1025,Emma,Smith,76,B,Mackillop
1026,Noah,Patel,82,A,Kendall
1027,Sophie,Lee,69,C,O'Brien
```

**Structure breakdown:**

- **Line 1 (header row):** Field names separated by commas
- **Lines 2-6 (data rows):** Each line = one complete record
- **Each value separated by a delimiter** (comma in this case)
- Can be opened directly in spreadsheet software
- Represents a 2D array (rows × columns)

**Each line = a record**

**Each value separated by a delimiter (comma)**

**Reading this in C#:**

```csharp
// Read all lines from CSV file
string[] lines = File.ReadAllLines("students.csv");

// First line is the header (skip it when processing data)
Console.WriteLine("Header: " + lines[0]);

// Process data rows (starting from index 1)
for (int i = 1; i < lines.Length; i++)
{
    // Split each line by comma to get individual fields
    string[] fields = lines[i].Split(',');

    string studentID = fields[0];   // "1023"
    string firstName = fields[1];   // "Aisha"
    string lastName = fields[2];    // "Khan"
    string score = fields[3];       // "87"
    string grade = fields[4];       // "A"
    string house = fields[5];       // "Kendall"

    Console.WriteLine($"{firstName} {lastName} scored {score} ({grade})");
}
```

!!! tip "When to use CSV"
    - Tabular data with consistent fields across all records
    - Need to transfer data between programs and spreadsheets
    - Simple row/column structure
    - Smaller file size compared to XML

---

## Example 3 — XML (hierarchical / nested)

**Scenario:** A library system needs to store book information with multiple authors and categories, supporting complex nested relationships.

**File: library.xml**

```xml
<?xml version="1.0" encoding="utf-8"?>
<library>
  <!-- First book in the library -->
  <book id="101">
    <title>Clean Code</title>
    <author>Robert Martin</author>
    <year>2008</year>
    <categories>
      <category>Programming</category>
      <category>Software Engineering</category>
    </categories>
    <available>true</available>
  </book>

  <!-- Second book with multiple authors -->
  <book id="102">
    <title>Design Patterns</title>
    <authors>
      <author>Erich Gamma</author>
      <author>Richard Helm</author>
      <author>Ralph Johnson</author>
      <author>John Vlissides</author>
    </authors>
    <year>1994</year>
    <categories>
      <category>Programming</category>
      <category>Design</category>
    </categories>
    <available>false</available>
  </book>

  <!-- Third book with nested publisher information -->
  <book id="103">
    <title>The Pragmatic Programmer</title>
    <author>Andrew Hunt</author>
    <publisher>
      <name>Addison-Wesley</name>
      <location>Boston</location>
    </publisher>
    <year>1999</year>
    <categories>
      <category>Programming</category>
    </categories>
    <available>true</available>
  </book>
</library>
```

**Structure breakdown:**

- **Prolog (line 1):** `<?xml version="1.0" encoding="utf-8"?>` declares this is an XML file
- **Root element:** `<library>` wraps all data
- **Parent elements:** Each `<book>` contains child elements
- **Child elements:** `<title>`, `<author>`, `<year>`, etc.
- **Nested structures:** `<categories>` contains multiple `<category>` tags
- **Self-describing:** Tags make it obvious what each value represents
- **Attributes:** `id="101"` provides additional metadata

**Tags make it obvious what each value represents**

**Nested structure supports more complex data**

**Why XML is better here than CSV:**

- Books can have **different numbers of authors** (1 author vs 4 authors)
- Books can have **multiple categories**
- **Nested publisher information** can't be represented well in flat CSV
- Structure can **evolve** (add new fields without breaking existing data)

**Reading this in C# using XDocument:**

```csharp
using System.Xml.Linq;

// Load the XML file
XDocument doc = XDocument.Load("library.xml");

// Get all book elements
var books = doc.Descendants("book");

// Process each book
foreach (var book in books)
{
    // Extract data using tag names
    string id = book.Attribute("id").Value;
    string title = book.Element("title").Value;
    string year = book.Element("year").Value;
    string available = book.Element("available").Value;

    Console.WriteLine($"Book {id}: {title} ({year})");

    // Handle multiple authors (if present)
    var authors = book.Descendants("author");
    foreach (var author in authors)
    {
        Console.WriteLine($"  Author: {author.Value}");
    }

    // Handle multiple categories
    var categories = book.Descendants("category");
    foreach (var category in categories)
    {
        Console.WriteLine($"  Category: {category.Value}");
    }

    Console.WriteLine($"  Available: {available}\n");
}
```

!!! tip "When to use XML"
    - Hierarchical/nested data structures
    - Variable number of child elements (e.g., multiple authors)
    - Self-describing data (tags explain meaning)
    - Need flexibility for structural changes
    - Data with parent-child relationships

---

## Comparison Summary

| Feature | TXT | CSV | XML |
|---------|-----|-----|-----|
| **Structure** | Unstructured or simple patterns | Rows and columns with delimiter | Hierarchical with tags |
| **Best for** | Simple settings/config | Tabular data | Complex nested data |
| **File size** | Smallest | Small | Largest |
| **Human readable** | Very easy | Easy | Easy but verbose |
| **Flexibility** | Limited | Limited | Very flexible |
| **Example use** | Game settings | Student grades | Family trees, product catalogs |

---

## Example 4 — Comparing file types for the same data

**Scenario:** Store information about 3 employees.

### TXT version (employees.txt)

```
John Smith
Developer
50000
Sarah Jones
Manager
75000
Mike Chen
Designer
55000
```

**Problem:** No clear structure - which line is name/role/salary? Hard to parse reliably.

---

### CSV version (employees.csv)

```
Name,Role,Salary
John Smith,Developer,50000
Sarah Jones,Manager,75000
Mike Chen,Designer,55000
```

**Better:** Clear columns, easy to process as a table, works well in spreadsheets.

---

### XML version (employees.xml)

```xml
<?xml version="1.0" encoding="utf-8"?>
<company>
  <employee id="101">
    <name>John Smith</name>
    <role>Developer</role>
    <salary currency="AUD">50000</salary>
  </employee>
  <employee id="102">
    <name>Sarah Jones</name>
    <role>Manager</role>
    <salary currency="AUD">75000</salary>
  </employee>
  <employee id="103">
    <name>Mike Chen</name>
    <role>Designer</role>
    <salary currency="AUD">55000</salary>
  </employee>
</company>
```

**Most flexible:** Self-describing tags, can add attributes (id, currency), can easily extend with nested elements (e.g., contact details, skills).

---

!!! warning "Exam Tip"
    When comparing file types in an exam:

    1. **Describe the structure** of each format
    2. **Explain why** one is better for the specific scenario
    3. Use phrases like:
        - "CSV uses delimiters to separate fields in a tabular structure"
        - "XML uses tags that describe what each field contains"
        - "XML is better here because the data is hierarchical/nested"
        - "CSV is better here because the data is tabular with consistent fields"
