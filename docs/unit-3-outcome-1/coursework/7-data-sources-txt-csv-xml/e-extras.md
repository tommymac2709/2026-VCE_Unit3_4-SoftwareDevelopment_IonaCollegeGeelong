# e. Extras

Below is clean, classroom-ready C# file I/O for each format. Students can be given this and focus on using it correctly.

!!! info "Note"
    Use a relative file path such as `"data/students.csv"` (and ensure the folder exists), or an absolute path if your SAC setup requires it.

---

## 1) TXT — read all lines, add a line, write back

```csharp
using System;
using System.Collections.Generic;
using System.IO;

public static class TxtFileHelper
{
    // Path constant (recommended for Unit 3)
    private const string TXT_PATH = "data/settings.txt";

    public static List<string> LoadLines()
    {
        if (!File.Exists(TXT_PATH)) return new List<string>();
        return new List<string>(File.ReadAllLines(TXT_PATH));
    }

    public static void AddLineAndSave(string newLine)
    {
        var lines = LoadLines();
        lines.Add(newLine);
        File.WriteAllLines(TXT_PATH, lines);
    }
}
```

---

## 2) CSV — load rows into objects, add a row, save back

This example assumes a simple CSV with a header:

```
StudentID,FirstName,LastName,Score
```

```csharp
using System;
using System.Collections.Generic;
using System.IO;

public class StudentResult
{
    public int StudentID { get; set; }
    public string FirstName { get; set; } = "";
    public string LastName { get; set; } = "";
    public int Score { get; set; }
}

public static class CsvFileHelper
{
    // Path constant (recommended for Unit 3)
    private const string CSV_PATH = "data/students.csv";

    public static List<StudentResult> LoadStudentResults()
    {
        var results = new List<StudentResult>();
        if (!File.Exists(CSV_PATH)) return results;

        var lines = File.ReadAllLines(CSV_PATH);
        if (lines.Length <= 1) return results; // header only or empty

        for (int i = 1; i < lines.Length; i++) // start after header
        {
            var parts = lines[i].Split(','); // delimiter = comma

            // Basic safety check
            if (parts.Length != 4) continue;

            results.Add(new StudentResult
            {
                StudentID = int.Parse(parts[0]),
                FirstName = parts[1],
                LastName = parts[2],
                Score = int.Parse(parts[3])
            });
        }

        return results;
    }

    public static void SaveStudentResults(List<StudentResult> results)
    {
        var lines = new List<string> { "StudentID,FirstName,LastName,Score" };

        foreach (var r in results)
        {
            lines.Add($"{r.StudentID},{r.FirstName},{r.LastName},{r.Score}");
        }

        File.WriteAllLines(CSV_PATH, lines);
    }
}
```

!!! warning "Teacher note"
    CSV gets tricky if fields can contain commas (e.g. surnames like "Smith, Jr"). That's one reason XML can be preferable in messy real data.

---

## 3) XML — load and save using XDocument

This stores a list of `<student>` elements.

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

## 40+ Exam Tip (highly examinable)

!!! tip "When asked to justify CSV vs XML, include:"
    - **Structure** (delimiter vs tags / tree)
    - **Impact** on flexibility, interoperability and readability

    That is exactly what examiner reports praise in high-scoring responses.
