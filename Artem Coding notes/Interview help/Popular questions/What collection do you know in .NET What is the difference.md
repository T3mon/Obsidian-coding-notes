In .NET, [[Collections|collections]] are used to store groups of related objects. The .NET framework provides a variety of collection classes, each designed for different scenarios and performance needs. Here's an overview of some common collections and their differences:

#### Dictionary<TKey, TValue>
- **Namespace:** `System.Collections.Generic`
- **Description:** Key-value pair collection.
- **Usage:** Ideal for fast lookups based on unique keys.
- **Example:**
  ```csharp
  Dictionary<string, int> ages = new Dictionary<string, int>();
  ages["Alice"] = 30;
  ```

- [ ] MORE COLLECTIONS HERE