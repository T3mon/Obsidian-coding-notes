Idempotency is like a special "repeat-safe" quality for actions. Imagine you're pressing an elevator button:
1. Pressing it once calls the elevator.
2. Pressing it multiple times doesn't call multiple elevators or make it come faster.
3. The end result is the same whether you pressed it once or ten times.

1. For GET:
```csharp
[HttpGet("{id}")]
public ActionResult<Book> GetBook(int id)
{
    var book = _books.FirstOrDefault(b => b.Id == id);
    if (book == null)
        return NotFound();
    return book;
}
```
Idempotency is guaranteed because:
- We're only reading data, not modifying it.
- The same ID will always return the same book (or NotFound if it doesn't exist).

2. For PUT:
```csharp
[HttpPut("{id}")]
public IActionResult UpdateBook(int id, Book book)
{
    var existingBook = _books.FirstOrDefault(b => b.Id == id);
    if (existingBook == null)
        return NotFound();

    existingBook.Title = book.Title;
    existingBook.Author = book.Author;
    
    return NoContent();
}
```
Idempotency is guaranteed because:
- We're updating an existing resource based on its ID.
- Multiple identical updates will result in the same final state.
- We're not creating new resources or changing the ID.

3. For DELETE:
```csharp
[HttpDelete("{id}")]
public IActionResult DeleteBook(int id)
{
    var book = _books.FirstOrDefault(b => b.Id == id);
    if (book == null)
        return NotFound();

    _books.Remove(book);
    return NoContent();
}
```
Idempotency is guaranteed because:
- We first check if the book exists.
- We only remove the book if it exists.
- Subsequent calls for a non-existent book will just return NotFound, not changing the state.

The key aspects that ensure idempotency are:
1. Using unique identifiers (like ID) to target specific resources.
2. Checking for existence before modifying or deleting.
3. Ensuring that repeated operations on the same resource produce the same result.
4. Not creating new resources or side effects on repeated calls.

In contrast, the POST method is typically not idempotent because it often creates new resources:

```csharp
[HttpPost]
public ActionResult<Book> CreateBook(Book book)
{
    book.Id = _nextId++;
    _books.Add(book);
    return CreatedAtAction(nameof(GetBook), new { id = book.Id }, book);
}
```
This is not idempotent because:
- Each call creates a new book with a new ID.
- Repeated calls with the same data will create multiple books.

To make POST idempotent, you'd need to implement additional logic, like checking for existing resources based on some unique attribute before creating a new one. However, this is not typical for POST operations in RESTful APIs.