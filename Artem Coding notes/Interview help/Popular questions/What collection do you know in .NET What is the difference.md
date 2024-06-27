In .NET, collections are used to store groups of related objects. The .NET framework provides a variety of collection classes, each designed for different scenarios and performance needs. Here's an overview of some common collections and their differences:

### Common Collections in .NET

1. **ArrayList**
    - **Namespace:** `System.Collections`
    - **Description:** A non-generic collection that can store items of any type.
    - **Features:**
        - Automatically resizes as items are added.
        - Provides indexed access to elements.
    - **Drawbacks:**
        - Not type-safe since it stores `object` references.
        - Less performant compared to generic collections due to boxing/unboxing.
- 
2. **List<T>**
    
    - **Namespace:** `System.Collections.Generic`
    - **Description:** A generic collection that stores elements of a specified type.
    - **Features:**
        - Type-safe and avoids boxing/unboxing.
        - Provides indexed access.
        - Automatically resizes as elements are added.
    - **Use Case:** When you need a dynamic array with type safety.
    
    csharp
    
    Копировать код
    
    `List<int> intList = new List<int>(); intList.Add(1); intList.Add(2);`
    
3. **Dictionary<TKey, TValue>**
    
    - **Namespace:** `System.Collections.Generic`
    - **Description:** A collection of key-value pairs.
    - **Features:**
        - Provides fast lookups, adds, and removes by key.
        - Keys must be unique.
    - **Use Case:** When you need to store and quickly retrieve data using keys.
    
    csharp
    
    Копировать код
    
    `Dictionary<string, int> dict = new Dictionary<string, int>(); dict.Add("One", 1); dict.Add("Two", 2);`
    
4. **HashSet<T>**
    
    - **Namespace:** `System.Collections.Generic`
    - **Description:** A collection of unique elements.
    - **Features:**
        - Provides high-performance set operations like union and intersection.
        - Does not allow duplicate elements.
    - **Use Case:** When you need a collection of unique items.
    
    csharp
    
    Копировать код
    
    `HashSet<int> set = new HashSet<int>(); set.Add(1); set.Add(2);`
    
5. **Queue<T>**
    
    - **Namespace:** `System.Collections.Generic`
    - **Description:** A first-in, first-out (FIFO) collection.
    - **Features:**
        - Elements are added at the end and removed from the front.
    - **Use Case:** When you need a FIFO collection, such as for task scheduling.
    
    csharp
    
    Копировать код
    
    `Queue<string> queue = new Queue<string>(); queue.Enqueue("First"); queue.Enqueue("Second"); string first = queue.Dequeue();`
    
6. **Stack<T>**
    
    - **Namespace:** `System.Collections.Generic`
    - **Description:** A last-in, first-out (LIFO) collection.
    - **Features:**
        - Elements are added and removed from the top.
    - **Use Case:** When you need a LIFO collection, such as for undo functionality.
    
    csharp
    
    Копировать код
    
    `Stack<string> stack = new Stack<string>(); stack.Push("First"); stack.Push("Second"); string top = stack.Pop();`
    
7. **LinkedList<T>**
    
    - **Namespace:** `System.Collections.Generic`
    - **Description:** A doubly linked list.
    - **Features:**
        - Allows efficient insertion and removal of elements at any position.
        - Does not provide indexed access.
    - **Use Case:** When you need frequent insertions and deletions at both ends.
    
    csharp
    
    Копировать код
    
    `LinkedList<int> linkedList = new LinkedList<int>(); linkedList.AddLast(1); linkedList.AddFirst(2);`
    

### Differences Between Collections

- **ArrayList vs. List<T>**
    
    - `ArrayList` is non-generic and can store any type of object, which requires boxing/unboxing for value types.
    - `List<T>` is generic, type-safe, and performs better due to the absence of boxing/unboxing.
- **Dictionary<TKey, TValue> vs. HashSet<T>**
    
    - `Dictionary<TKey, TValue>` stores key-value pairs and allows fast lookups by key.
    - `HashSet<T>` only stores unique values and is ideal for set operations.
- **Queue<T> vs. Stack<T>**
    
    - `Queue<T>` operates on a FIFO basis, suitable for sequential processing.
    - `Stack<T>` operates on a LIFO basis, suitable for tasks requiring reversal of order.
- **List<T> vs. LinkedList<T>**
    
    - `List<T>` provides fast indexed access but is less efficient for insertions/deletions in the middle.
    - `LinkedList<T>` allows efficient insertions/deletions at any position but does not support indexed access.

Each collection serves different use cases based on performance characteristics and specific requirements. Choosing the right collection depends on the operations you need to perform and the nature of the data you are working with.