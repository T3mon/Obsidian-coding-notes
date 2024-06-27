**System.Collections (simple non-generic collection classes)**  
**System.Collections.Generic (generic or typed collection classes)**  
**System.Collections.Specialized (specialized collection classes)**  
**System.Collections.Concurrent (for concurrent task execution and multithreaded access)**

The foundation for creating all [collections](https://learn.microsoft.com/en-us/dotnet/api/system.collections?view=net-8.0#interfaces) is the implementation of the `IEnumerator` and `IEnumerable` interfaces.
![[Pasted image 20240627220434.png]]
---
# System.Collections namespace:
- **ArrayList:**  
    A class for a simple collection of objects. Implements the `IList`, `ICollection`, and `IEnumerable` interfaces.
- **BitArray:**  
    A collection class containing an array of bit values. Implements the `ICollection` and `IEnumerable` interfaces.
- **Hashtable:**  
    A collection class representing a hash table and storing a set of "key-value" pairs.
- **Queue:**  
    A queue class operating on the FIFO (first in, first out) principle. Implements the `ICollection` and `IEnumerable` interfaces.
- **SortedList:**  
    A collection class storing sets of "key-value" pairs sorted by the key. Implements the `ICollection`, `IDictionary`, and `IEnumerable` interfaces.
- **Stack:**  
    A stack class.

---


  