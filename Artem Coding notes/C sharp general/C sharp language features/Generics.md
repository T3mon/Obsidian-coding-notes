The C# compiler generates separate code for each specific type used in a generic class.
- `GenericList<int>`: replaces `T` with `int`.
- `GenericList<string>`: replaces `T` with `string`.
### Covariance and Contravariance for Interfaces:
Covariance (out):
- Allows using a more specific type (subtype) in place of a more general type (base type).
- Applied to return types (output parameters).
```csharp
public interface ICovariant<out T>
{
	T Get();
}
public class BaseClass { }
public class DerivedClass : BaseClass { }

public class CovariantExample : ICovariant<DerivedClass>
{
	public DerivedClass Get()
	{
		return new DerivedClass();
	}
}
static void Main()
{
	ICovariant<DerivedClass> derived = new CovariantExample();
	ICovariant<BaseClass> baseClass = derived;
	BaseClass item = baseClass.Get();
}
```

Contravariance (in):
- Allows using a more general type in place of a more specific type.
- Applied to input parameters.
```csharp 
public interface IContravariant<in T>
{
	void Set(T item);
}

public class BaseClass { }
public class DerivedClass : BaseClass { }

public class ContravariantExample : IContravariant<BaseClass>
{
	public void Set(BaseClass item)
	{
	}
}

static void Main()
{
	IContravariant<BaseClass> baseClass = new ContravariantExample();
	IContravariant<DerivedClass> derived = baseClass;
	derived.Set(new DerivedClass());
}
```