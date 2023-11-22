---
tags:
  - best-practices
---
# Best Practices

- Never use `.Wait()` or `.Result()`
	- Always use `await` (does not lock current thread)
	- If synchronous, use `.GetAwaiter().GetResult()` (it still lock current thread and create a new one but it is better)
- Fire and forget tasks
	- Use `SafeFireAndForget` (Nuget: AsyncAwaitBestPractices)
 - Avoid `return await` if there is only one place in the method that returns because it will just use a thread from the thread pool, and it is not necessary
	- Remove `async` keyword
		- Except: In `try/catch` blocks
		- Except: In `using( .. )` blocks
- Utilize `.ConfigureAwait(false)`
	-  Except: When needing to return to calling thread, this happens mostly on UI project
	-  Note: Only works when framework is using SynchronizationContext (frameworks which has UI use it, for example .NET MAUI)
- Utilize `ValueTask`
	- When a method's "hot path" doesn't call `await`
 -  `IAsyncEnumerable` for streaming data
	- Allows us to update UI as data arrives
	- Better user experience
	- Use `[EnumeratorCancellation]` for `CancellationToken`
- `WaitAsync(CancellationToken)` 
	- Append to any async method missing a `CancellationToken` parameter
 -  `IAsyncDisposable`
	- The `await` executes at the end of the `using` block
	- Can append `ConfigureAwait(false)`