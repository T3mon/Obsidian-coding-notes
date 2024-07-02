1. Delegates:
Delegates are type-safe function pointers. They allow you to treat methods as objects.
```csharp
public delegate void MyDelegate(string message);
```
Reasons to use:
- When you need to pass methods as parameters
- To implement callback mechanisms
- As a foundation for events
2. Events:
Events are a way to notify subscribers when something happens in your code. They're built on top of delegates.
```csharp
public event EventHandler MyEvent;
```
Reasons to use:
- To implement the Observer pattern
- When you need a publish-subscribe model
- To create loosely coupled systems
3. Func:
Func is a generic delegate type provided by .NET for methods that return a value.
```csharp
Func<int, int, string> myFunc = (a, b) => (a + b).ToString();
```
Reasons to use:
- When you need a concise way to work with methods that return values
- In LINQ queries
- For lambda expressions
4. Action:
Action is a generic delegate type for methods that don't return a value (void methods).
```csharp
Action<string> myAction = message => Console.WriteLine(message);
```
Reasons to use:
- When you need a concise way to work with void methods
- In scenarios where you don't need a return value
- For simple callbacks or event handlers
