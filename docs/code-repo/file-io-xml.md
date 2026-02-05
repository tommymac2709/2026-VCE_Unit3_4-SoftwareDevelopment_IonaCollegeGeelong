# XML File I/O

!!! info "When to Use XML Files"
    Use XML for hierarchical/nested data structures where records may have variable numbers of child elements. Self-describing and flexible.

---

## XML File Helper Class

??? note "Click to view XmlFileHelper.cs"
    ```csharp
    using System;
    using System.Collections.Generic;
    using System.IO;
    using System.Xml.Linq;

    public static class XmlFileHelper
    {
        // Path constant (recommended for Unit 3)
        private const string XML_PATH = "data/students.xml";

        public static List<StudentResult> LoadFromXml()
        {
            var results = new List<StudentResult>();
            if (!File.Exists(XML_PATH)) return results;

            var doc = XDocument.Load(XML_PATH);

            foreach (var s in doc.Root?.Elements("student") ?? new List<XElement>())
            {
                results.Add(new StudentResult
                {
                    StudentID = (int)s.Element("id")!,
                    FirstName = (string)s.Element("firstName")!,
                    LastName  = (string)s.Element("lastName")!,
                    Score     = (int)s.Element("score")!
                });
            }

            return results;
        }

        public static void SaveToXml(List<StudentResult> results)
        {
            var doc = new XDocument(
                new XElement("students",
                    results.ConvertAll(r =>
                        new XElement("student",
                            new XElement("id", r.StudentID),
                            new XElement("firstName", r.FirstName),
                            new XElement("lastName", r.LastName),
                            new XElement("score", r.Score)
                        )
                    )
                )
            );

            doc.Save(XML_PATH);
        }
    }
    ```

---

## Usage Example

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

    Console.WriteLine($"Book {id}: {title} ({year})");

    // Handle multiple authors (if present)
    var authors = book.Descendants("author");
    foreach (var author in authors)
    {
        Console.WriteLine($"  Author: {author.Value}");
    }
}
```

---

## Example XML File Structure

```xml
<?xml version="1.0" encoding="utf-8"?>
<library>
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

  <book id="102">
    <title>Design Patterns</title>
    <authors>
      <author>Erich Gamma</author>
      <author>Richard Helm</author>
      <author>Ralph Johnson</author>
      <author>John Vlissides</author>
    </authors>
    <year>1994</year>
    <available>false</available>
  </book>
</library>
```

!!! tip "Advantages of XML"
    - Can handle variable numbers of child elements (multiple authors)
    - Self-describing with tags
    - Can handle commas/line breaks in data without breaking structure
    - Extensible and flexible
