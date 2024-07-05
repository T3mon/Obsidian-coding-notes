 ==Objects of a superclass should be replaceable with objects of its subclasses without affecting the correctness of the program==. In other words, a subclass should be able to substitute its parent class without causing any unexpected behavior.

Let's explore this principle with examples:
#### 1. Correct LSP implementation:
```csharp
public abstract class Shape
{
    public abstract double Area();
}

public class Rectangle : Shape
{
    public virtual double Width { get; set; }
    public virtual double Height { get; set; }

    public override double Area() => Width * Height;
}

public class Square : Shape
{
    public double Side { get; set; }

    public override double Area() => Side * Side;
}

public class Program
{
    public static void Main()
    {
        Shape rect = new Rectangle { Width = 5, Height = 4 };
        Shape square = new Square { Side = 5 };

        Console.WriteLine(rect.Area());   // Output: 20
        Console.WriteLine(square.Area()); // Output: 25

        List<Shape> shapes = new List<Shape> { rect, square };
        foreach (var shape in shapes)
        {
            Console.WriteLine(shape.Area());
        }
    }
}
```

In this example, both Rectangle and Square inherit from Shape and implement the Area() method. They can be used interchangeably wherever a Shape is expected, adhering to the LSP.
## 2. Incorrect LSP implementation:
```csharp
public class Bird
{
    public virtual void Fly() => Console.WriteLine("Flying");
}

public class Ostrich : Bird
{
    public override void Fly() => throw new NotImplementedException("Can't fly");
}

// Usage
public class Program
{
    public static void Main()
    {
        Bird bird = new Bird();
        Bird ostrich = new Ostrich();

        MakeBirdFly(bird);    // Works fine
        MakeBirdFly(ostrich); // Throws exception, violating LSP
    }

    public static void MakeBirdFly(Bird bird)
    {
        bird.Fly();
    }
}
```

In this example, Ostrich violates LSP because it can't be substituted for Bird without causing unexpected behavior (throwing an exception).
3. A more practical example:
```csharp
public interface IRepository<T>
{
    IEnumerable<T> GetAll();
    void Add(T entity);
}

public class ReadOnlyRepository<T> : IRepository<T>
{
    private readonly List<T> _entities = new List<T>();

    public IEnumerable<T> GetAll() => _entities;

    public virtual void Add(T entity) => _entities.Add(entity);
}

public class AuditedRepository<T> : ReadOnlyRepository<T>
{
    public override void Add(T entity)
    {
        // Log the addition
        Console.WriteLine($"Adding entity: {entity}");
        base.Add(entity);
    }
}

// Usage
public class Program
{
    public static void Main()
    {
        IRepository<string> repo1 = new ReadOnlyRepository<string>();
        IRepository<string> repo2 = new AuditedRepository<string>();

        AddEntity(repo1, "Entity 1");
        AddEntity(repo2, "Entity 2");

        Console.WriteLine(string.Join(", ", repo1.GetAll()));
        Console.WriteLine(string.Join(", ", repo2.GetAll()));
    }

    public static void AddEntity(IRepository<string> repo, string entity)
    {
        repo.Add(entity);
    }
}
```

In this example, both ReadOnlyRepository and AuditedRepository adhere to the LSP. They can be used interchangeably wherever an IRepository is expected, with AuditedRepository adding extra functionality without breaking the contract.

Key points to remember about LSP:
1. Subtypes must be substitutable for their base types without altering the correctness of the program.
2. Overridden methods shouldn't throw new exceptions that aren't part of the base method's contract.
3. Subclasses should respect the behavior that clients expect of the base class.
4. Preconditions can't be strengthened in a subtype.
5. Postconditions can't be weakened in a subtype.
6. Invariants of the supertype must be preserved in the subtype.

By adhering to the Liskov Substitution Principle, you create more robust and flexible software designs that are easier to extend and maintain over time.