What is the purpose of async and await in C#?

1. The async and await keywords are used to write asynchronous code in C#.
2. They allow you to run non-blocking operations, like long-running tasks, without freezing the application.
3. The async keyword marks a method as asynchronous, while the await keyword is used to pause the execution until the asynchronous task is completed.

Performance: async and await improve performance by freeing up the main thread while waiting for tasks like file I/O, network requests, or database calls. This helps avoid blocking the UI or holding up resources unnecessarily, allowing the application to remain responsive and to process other tasks simultaneously.

The return type of an async method can be Task or Task<T>, or void (in the case of event handlers).
Task or Task<T> allows the caller to check the status of the operation. Avoid using void in asynchronous methods because exceptions cannot be caught with it.

Task represents an operation that returns no value. Task<T> represents an operation that returns a result of type T.
In async methods, exceptions are thrown and can be caught at the point where the task is awaited. If an exception occurs, it can be caught using a try-catch block around the await keyword. If async returns a Task and the caller does not await it, the exception might go unnoticed.

async and await can be used on the UI to keep the application responsive during long-running tasks.
