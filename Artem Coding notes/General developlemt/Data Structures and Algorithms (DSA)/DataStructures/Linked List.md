### Singly Linked List
![[Pasted image 20240708185417.png]]

| Operation                 | Time Complexity                                                            |
| ------------------------- | -------------------------------------------------------------------------- |
| Access by index           | O(n)                                                                       |
| Search                    | O(n)                                                                       |
| Insertion (at the end)    | O(1) if we have a pointer to the last node, otherwise O(n)                 |
| Insertion (in the middle) | O(n) (O(1) if we have a pointer to the node before the new node)           |
| Deletion (last element)   | O(n)                                                                       |
| Deletion (from middle)    | O(n) (O(1) if we have a pointer to the node before the node to be deleted) |
|                           |                                                                            |
### Doubly Linked List
![[Pasted image 20240708190155.png]]

| Operation                 | Time Complexity                                                           |
| ------------------------- | ------------------------------------------------------------------------- |
| Access by index           | O(n)                                                                      |
| Search                    | O(n)                                                                      |
| Insertion (at the end)    | O(1)                                                                      |
| Insertion (in the middle) | O(n) (O(1) if we have a pointer to the node before or after the new node) |
| Deletion (last element)   | O(1)                                                                      |
| Deletion (from middle)    | O(n) (O(1) if we have a pointer to the node to be deleted)                |
#### C# Methods

| Method                                                                                                               | Description                                                                                                              |
| -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **AddAfter**                                                                                                         | Adds a new node or value after an existing node in the LinkedList.                                                       |
| **AddBefore**                                                                                                        | Adds a new node or value before an existing node in the LinkedList.                                                      |
| **[AddFirst](https://www.geeksforgeeks.org/c-adding-new-node-or-value-at-the-start-of-linkedlistt/)**                | Adds a new node or value at the start of the LinkedList.                                                                 |
| **[AddLast](https://www.geeksforgeeks.org/c-adding-new-node-or-value-at-the-end-of-linkedlistt/)**                   | Adds a new node or value at the end of the LinkedList.                                                                   |
| **[Clear()](https://www.geeksforgeeks.org/c-removing-all-nodes-from-linkedlistt/)**                                  | Removes all nodes from the LinkedList.                                                                                   |
| **[Contains(T)](https://www.geeksforgeeks.org/c-check-if-a-value-is-in-linkedlistt/)**                               | Determines whether a value is in the LinkedList.                                                                         |
| **[CopyTo(T[], Int32)](https://www.geeksforgeeks.org/c-copy-the-entire-linkedlistt-to-array/)**                      | Copies the entire LinkedList to a compatible one-dimensional Array, starting at the specified index of the target array. |
| **[Equals(Object)](https://www.geeksforgeeks.org/c-check-if-two-linkedlistt-objects-are-equal/)**                    | Determines whether the specified object is equal to the current object.                                                  |
| **[Find(T)](https://www.geeksforgeeks.org/c-find-the-first-node-in-linkedlistt-containing-the-specified-value/)**    | Finds the first node that contains the specified value.                                                                  |
| **[FindLast(T)](https://www.geeksforgeeks.org/c-find-the-last-node-in-linkedlistt-containing-the-specified-value/)** | Finds the last node that contains the specified value.                                                                   |
| **[GetEnumerator()](https://www.geeksforgeeks.org/c-getting-an-enumerator-that-iterates-through-linkedlistt/)**      | Returns an enumerator that iterates through the LinkedList.                                                              |
| **GetHashCode()**                                                                                                    | Serves as the default hash function.                                                                                     |
| **GetObjectData(SerializationInfo, StreamingContext)**                                                               | Implements the ISerializable interface and returns the data needed to serialize the LinkedList instance.                 |
| **GetType()**                                                                                                        | Gets the Type of the current instance.                                                                                   |
| **MemberwiseClone()**                                                                                                | Creates a shallow copy of the current Object.                                                                            |
| **OnDeserialization(Object)**                                                                                        | Implements the ISerializable interface and raises the deserialization event when the deserialization is complete.        |
| **[Remove(LinkedListNode)](https://www.geeksforgeeks.org/c-removing-the-specified-node-from-the-linkedlistt/)**      | Removes the specified node from the LinkedList.                                                                          |
| **[Remove(T)](https://www.geeksforgeeks.org/c-removing-first-occurrence-of-specified-value-from-linkedlistt/)**      | Removes the first occurrence of the specified value from the LinkedList.                                                 |
| **[RemoveFirst()](https://www.geeksforgeeks.org/c-removing-the-node-at-the-start-of-the-linkedlistt/)**              | Removes the node at the start of the LinkedList.                                                                         |
| **[RemoveLast()](https://www.geeksforgeeks.org/c-removing-the-node-at-the-end-of-linkedlistt/)**                     | Removes the node at the end of the LinkedList.                                                                           |
| **ToString()**                                                                                                       | Returns a string that represents the current object.                                                                     |
