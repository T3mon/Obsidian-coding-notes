Exception handling in C# is a way to manage errors or unexpected situations that occur during program execution. It uses a combination of `try`, `catch`, `finally`, and `throw` blocks.
1. **try block**: The `try` block is used in C# to enclose code that might throw an exception. If an ==exception is thrown, the code inside block is interrupted, and the system looks for a corresponding `catch` block== to handle the exception. If no matching `catch` block is found, the program terminates. Сan contain another `try` block. This is called nested `try` blocks.
2. **catch block**: Handles the exception. You can have multiple catch blocks for different types of exceptions.
3. **finally block**: Executes code regardless of whether an exception occurred or not. It’s often used for cleanup.
4. **throw statement**: Used to explicitly throw an exception.

Best practices:
- If you have multiple `catch` blocks, they should be ordered from most specific to most general
- `throw ex` can make it challenging to debug and trace the original source of the exception as you lose original exception’s stack trace
- Use `ex` parameter to get exception details: You can use the `ex` parameter in the `catch` block to get more information about the exception, such as the error message, stack trace, and inner exception.
- You should almost never have an empty catch block, at least log it
- If you are going to rethrow an exception use the "throw;" statement to rethrow it, or throw a new exception with the old exception "throw new InvalidOperationException(ex);", don't rethrow the exception by saying "throw ex;", that will replace the StackTrace and make the exception data much less useful
- Avoid try/catch blocks where the catch just rethrows
- It is recommended to inherit custom exceptions directly from the `Exception` class

