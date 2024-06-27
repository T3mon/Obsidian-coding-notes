- **[Encapsulation](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/object-oriented/#encapsulation)**: Bundling the data (variables) and code (methods) together as a single unit known as a class. **Access modification**.
![[bwm9m69tpmp91.webp]]
- **[Inheritance](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/object-oriented/inheritance)**: Creating new classes that **reuse, extend, and modify the behavior** defined in other classes. ![[Pasted image 20240627151717.png]] 

- **[Polymorphism](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/object-oriented/polymorphism)**: Using a unified interface to call different underlying forms of methods. 
 ```csharp
 class Polygon
 {
     public virtual void render() => 
         Console.WriteLine("Rendering Polygon...");`
 }

 class Square : Polygon
 {
     public override void render() =>
         Console.WriteLine("Rendering Square...");`
 } ```
*Method Overriding is an example of Runtime/Dynamic polymorphism*
![[Pasted image 20240627150104.png]] *Function overloading/Operator overloading is an example of compile time/Static polymorphism*

- **Abstraction**: Simplifying complex reality by modeling classes appropriate to the problem. Implemented using abstract classes and methods. An abstract class cannot be instantiated, and must be inherited by a derived class in order to be used. Abstract classes are created using the **abstract** keyword, and **can contain both abstract and non-abstract** members