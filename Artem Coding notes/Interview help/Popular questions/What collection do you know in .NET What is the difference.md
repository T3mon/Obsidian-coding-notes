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
#### HashSet<T>

- **Namespace:** `System.Collections.Generic`
- **Description:** Collection of unique elements.
- **Usage:** Used when uniqueness of elements is important.
- **Example:**
    
    csharp
    
    Копировать код
    
    `HashSet<int> uniqueNumbers = new HashSet<int>(); uniqueNumbers.Add(1);`
    

#### Queue<T>

- **Namespace:** `System.Collections.Generic`
- **Description:** First-in, first-out (FIFO) collection.
- **Usage:** For implementing scenarios like breadth-first search.
- **Example:**
    
    csharp
    
    Копировать код
    
    `Queue<string> queue = new Queue<string>(); queue.Enqueue("first");`
    

#### Stack<T>

- **Namespace:** `System.Collections.Generic`
- **Description:** Last-in, first-out (LIFO) collection.
- **Usage:** Used in scenarios like depth-first search or function call stack.
- **Example:**
    
    csharp
    
    Копировать код
    
    `Stack<int> stack = new Stack<int>(); stack.Push(1);`
    

#### LinkedList<T>

- **Namespace:** `System.Collections.Generic`
- **Description:** Doubly linked list collection.
- **Usage:** When frequent insertions or deletions in the middle are required.
- **Example:**
    
    csharp
    
    Копировать код
    
    `LinkedList<int> linkedList = new LinkedList<int>(); linkedList.AddLast(1);`
    

These collections offer different data structures tailored to specific needs, providing flexibility and efficiency depending on the requirements of your application.