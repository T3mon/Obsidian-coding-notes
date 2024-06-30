### Value Types

- **Storage**: Stored on the stack.
- **Memory Allocation**: The actual data is stored directly in the variable.
- **Access**: Direct access to the value.
- **Examples**: `int`, `float`, `double`, `struct`, `enum`.
- **Characteristics**:
    - **Value Copying**: When assigned to another variable, a copy of the value is made.
    - **Memory Efficiency**: Typically more memory-efficient for small data.
    - **Default Initialization**: Initialized to their default value (e.g., `0` for `int`).
**Example:**
```csharp
`int a = 5; int b = a; // b is a copy of a a = 10; Console.WriteLine(b); // Outputs 5`
```
### Reference Types (Object Types)
- **Storage**: Stored on the heap.
- **Memory Allocation**: The variable stores a reference (or pointer) to the actual data.
- **Access**: Indirect access via the reference.
- **Examples**: `class`, `interface`, `delegate`, `string`, `object`.
- **Characteristics**:
    - **Reference Copying**: When assigned to another variable, only the reference is copied, not the actual data.
    - **Memory Usage**: May involve more overhead due to heap allocation and garbage collection.
    - **Default Initialization**: Initialized to `null` by default.
**Example:**
```csharp
`class Person { public string Name; } Person p1 = new Person { Name = "Alice" }; Person p2 = p1; // p2 references the same object as p1 p1.Name = "Bob"; Console.WriteLine(p2.Name); // Outputs "Bob"`
```
### Summary Table

| Feature                | Value Types              | Reference Types (Object Types)   |
| ---------------------- | ------------------------ | -------------------------------- |
| Storage                | Stack                    | Heap                             |
| Memory Allocation      | Direct                   | Indirect (reference)             |
| Access                 | Direct                   | Indirect (via reference)         |
| Assignment             | Copies the value         | Copies the reference             |
| Default Initialization | Default value (e.g., 0)  | `null`                           |
| Examples               | `int`, `float`, `struct` | `class`, `interface`, `delegate` |
