# TXT File I/O

!!! info "When to Use TXT Files"
    Use TXT files for simple configuration settings or small amounts of unstructured data.

---

## TXT File Helper Class

??? note "Click to view TxtFileHelper.cs"
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

## Usage Example

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

---

## Example TXT File Structure

```
theme=dark
fontSize=14
musicOn=true
username=PlayerOne
difficulty=medium
volume=75
```

!!! tip "Best Practice"
    Use a relative file path such as `"data/settings.txt"` and ensure the folder exists.
