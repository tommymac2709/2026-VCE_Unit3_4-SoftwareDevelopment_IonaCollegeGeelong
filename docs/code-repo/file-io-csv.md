# CSV File I/O

!!! info "When to Use CSV Files"
    Use CSV files for tabular data with consistent fields across all records. Easy to transfer between programs and spreadsheets.

---

## Student Result Class

```csharp
public class StudentResult
{
    public int StudentID { get; set; }
    public string FirstName { get; set; } = "";
    public string LastName { get; set; } = "";
    public int Score { get; set; }
}
```

---

## CSV File Helper Class

??? note "Click to view CsvFileHelper.cs"
    ```csharp
    using System;
    using System.Collections.Generic;
    using System.IO;

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

---

## Usage Example

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

    Console.WriteLine($"{firstName} {lastName} scored {score}");
}
```

---

## Example CSV File Structure

```
StudentID,FirstName,LastName,Score,Grade,House
1023,Aisha,Khan,87,A,Kendall
1024,Luca,Rossi,91,A,O'Brien
1025,Emma,Smith,76,B,Mackillop
```

!!! warning "Note"
    CSV gets tricky if fields can contain commas (e.g., surnames like "Smith, Jr"). That's one reason XML can be preferable for messy real data.
