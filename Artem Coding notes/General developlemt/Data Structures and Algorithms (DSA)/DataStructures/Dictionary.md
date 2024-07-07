#1 Reference: [https://dotnetos.org/blog/2022-03-28-dictionary-implementation/](https://dotnetos.org/blog/2022-03-28-dictionary-implementation/ "https://dotnetos.org/blog/2022-03-28-dictionary-implementation/") 
#2 Reference: https://habr.com/ru/articles/198104/

![[Pasted image 20240707160854.png]]
## Implementation

The most important implementation elements of the `Dictionary<TKey, TValue>`:
- `buckets` - set of elements with similar hashes
- `entries` - elements of the `Dictionary<TKey, TValue>`
- `freeList` - index of the first free place
- `freeCount` - the number of empty spaces in the array, not at the end
- `count` - the number of elements that are currently in the `Dictionary<TKey, TValue>`
- `version` - changes as the `Dictionary<TKey, TValue>` is modified

…and a few more equally important elements that `Entry` contains:
- `_key` - key to identify element with `TKey` type
- `_value` - value of an element with `TValue` type
- `_hashCode` - numeric value used to identify an object in hash-based collection
- `_next` - describes the next item in the `bucket`

## GetHashCode() and Equals() override

### Problem Example
```csharp
public class Person
{
    public string Name { get; set; } // NAME IS NOT IMMUTABLE
    public int Age { get; set; } //AGE IS NOT IMMUTABLE

    public override bool Equals(object obj)
    {
        if (obj == null || this.GetType() != obj.GetType())
            return false;

        Person other = (Person)obj;
        return this.Name == other.Name && this.Age == other.Age;
    }

    public override int GetHashCode()
    {
        int hash = 17;
        hash = hash * 31 + (Name != null ? Name.GetHashCode() : 0);
        hash = hash * 31 + Age.GetHashCode();
        return hash;
    }
}
```

```csharp
HashSet<Person> people = new HashSet<Person>();
Person person = new Person { Name = "Alice", Age = 30 };

people.Add(person); // Add object to collection

Console.WriteLine(people.Contains(person)); // True

person.Age = 31; // Change the Age property

Console.WriteLine(people.Contains(person)); // False, because the hash code changed

```
### Solutions

##### Immutability:
Make objects immutable so that their state cannot change after creation. This ensures that the hash code remains constant.
```csharp
public class Person
{
    public string Name { get; }
    public int Age { get; } 

    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }

    public override bool Equals(object obj)
    {
        if (obj == null || GetType() != obj.GetType())
            return false;

        Person other = (Person)obj;
        return Name == other.Name && Age == other.Age;
    }

    public override int GetHashCode()
    {
        unchecked
        {
            int hash = 17;
            hash = hash * 31 + (Name != null ? Name.GetHashCode() : 0);
            hash = hash * 31 + Age.GetHashCode();
            return hash;
        }
    }
}
```
##### Avoid Changing Significant Fields:
If making objects immutable is not possible, avoid changing fields that are used to compute the hash code while the object is in a hash-based collection.
```csharp
HashSet<Person> people = new HashSet<Person>();
Person person = new Person("Alice", 30);

people.Add(person); // Add object to collection

Console.WriteLine(people.Contains(person)); // True

// person.Age = 31; // Cannot change, as properties are read-only

// Create a new object for changes
Person updatedPerson = new Person("Alice", 31);

// Remove old object first, then add new one
people.Remove(person);
people.Add(updatedPerson);

Console.WriteLine(people.Contains(updatedPerson)); // True

```