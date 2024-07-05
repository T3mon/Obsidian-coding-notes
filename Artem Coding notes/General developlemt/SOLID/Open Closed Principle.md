Entities (classes, modules, functions, etc.) should be open for extension but closed for modification.
OCP is used to:
1. Create more flexible and maintainable code
2. Allow adding ==new functionality without changing existing code==
3. Reduce the risk of breaking existing functionality when making changes
4. Promote the use of abstractions and polymorphism
## 1. Without OCP:
```csharp
public class Rectangle
{
    public double Width { get; set; }
    public double Height { get; set; }
}

public class Circle
{
    public double Radius { get; set; }
}

public class AreaCalculator
{
    public double CalculateArea(object shape)
    {
        if (shape is Rectangle rectangle)
        {
            return rectangle.Width * rectangle.Height;
        }
        else if (shape is Circle circle)
        {
            return Math.PI * circle.Radius * circle.Radius;
        }
        throw new ArgumentException("Unsupported shape");
    }
}
```

In this example, adding a new shape would require modifying the AreaCalculator class, violating OCP.
## 2. With OCP:
```csharp
public abstract class Shape
{
    public abstract double CalculateArea();
}

public class Rectangle : Shape
{
    public double Width { get; set; }
    public double Height { get; set; }

    public override double CalculateArea() =>
         Width * Height;
}

public class Circle : Shape
{
    public double Radius { get; set; }

    public override double CalculateArea() =>
        Math.PI * Radius * Radius;
}

public class AreaCalculator
{
    public double CalculateArea(Shape shape) =>
		shape.CalculateArea();
    
}
```

Now, adding a new shape doesn't require modifying AreaCalculator. We can simply create a new class that inherits from Shape.
## 3. Another example using interfaces:
```csharp
public interface IDiscount
{
    decimal ApplyDiscount(decimal price);
}

public class RegularDiscount : IDiscount
{
    public decimal ApplyDiscount(decimal price) =>
        price * 0.9m; // 10% discount
}

public class PremiumDiscount : IDiscount
{
    public decimal ApplyDiscount(decimal price) =>
        price * 0.8m; // 20% discount
}

public class PriceCalculator
{
    public decimal CalcFinalPrice(decimal originalPrice, IDiscount discount) =>
        discount.ApplyDiscount(originalPrice);
}
```

In this example, we can add new discount types without modifying the PriceCalculator class.
## 4. Using the Strategy pattern to adhere to OCP:
```csharp
public interface ISortStrategy
{
    void Sort(List<int> list);
}

public class BubbleSort : ISortStrategy
{
    public void Sort(List<int> list) { /* Bubble sort implementation */ }
}

public class QuickSort : ISortStrategy
{
    public void Sort(List<int> list) { /* Quick sort implementation */ }
}

public class Sorter
{
    private readonly ISortStrategy _sortStrategy;

    public Sorter(ISortStrategy sortStrategy) =>
        _sortStrategy = sortStrategy;

    public void Sort(List<int> list) =>
        _sortStrategy.Sort(list);
}
```

This design allows adding new sorting algorithms without modifying the Sorter class.

By applying OCP, we create more flexible and extensible code that's easier to maintain and less prone to bugs when adding new functionality.