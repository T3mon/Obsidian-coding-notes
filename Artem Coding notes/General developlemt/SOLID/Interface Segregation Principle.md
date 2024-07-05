>"Clients should not be forced to depend on methods they do not use.'
  "Caller should not be able to see any more methods than it actually needs."
 
It's better to have many smaller, specific interfaces rather than a few large, general-purpose ones.
Key points of ISP:
1. ==Break large interfaces into smaller, more specific== ones.
2. Clients should only need to know about methods that are of interest to them.
3. Prevents classes from implementing unnecessary methods.
## 1. Violation of ISP:
```csharp
public interface IWorker
{
    void Work();
    void Eat();
    void Sleep();
}

public class Human : IWorker
{
    public void Work() { /* ... */ }
    public void Eat() { /* ... */ }
    public void Sleep() { /* ... */ }
}

public class Robot : IWorker
{
    public void Work() { /* ... */ }
    public void Eat() { throw new NotImplementedException(); }
    public void Sleep() { throw new NotImplementedException(); }
}
```

In this example, Robot is forced to implement Eat() and Sleep(), which it doesn't need.

## 2. Adhering to ISP:
```csharp
public interface IWorkable
{
    void Work();
}

public interface IEatable
{
    void Eat();
}

public interface ISleepable
{
    void Sleep();
}

public class Human : IWorkable, IEatable, ISleepable
{
    public void Work() { /* ... */ }
    public void Eat() { /* ... */ }
    public void Sleep() { /* ... */ }
}

public class Robot : IWorkable
{
    public void Work() { /* ... */ }
}
```

Now, Robot only implements the interface it needs (IWorkable), adhering to ISP.

3. Another example:

```csharp
public interface IPrinter
{
    void Print(string document);
}

public interface IScanner
{
    void Scan(string document);
}

public interface IFaxer
{
    void Fax(string document);
}

public class AllInOnePrinter : IPrinter, IScanner, IFaxer
{
    public void Print(string document) { /* ... */ }
    public void Scan(string document) { /* ... */ }
    public void Fax(string document) { /* ... */ }
}

public class SimplePrinter : IPrinter
{
    public void Print(string document) { /* ... */ }
}
```

In this example, different types of printers can implement only the interfaces they support, adhering to ISP.

By following ISP, you create more flexible and maintainable code, as classes only depend on the methods they actually use. This reduces the impact of changes and makes the system more modular.

 