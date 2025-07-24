---
id: asyncio
aliases:
  - Asyncio
tags: []
---

# Asyncio
```python
import asyncio
```

### Event loop
  Core that manages and distribute tasks. 
  Each task is handled by the event loop, either executing the task or pausing if it is waiting for some data/input.
  When A task awaits it is paused allowing other tasks to run. Once the wait is over after getting data/input the task is resumed.

__Event loop is started using:__
```python
    asyncio.run([coroutine])
```


### Coroutine
  Coroutines are functions that can be paused and resumed by _Event loop_
  When a Coroutine function is called it will return a coroutine object do not run the function like regular functions
  It must __await__ to be ran, either by running with _asyncio.run_ or _await_ keyword
  coroutine_functions can only be called from event loop or other async functions

__Coroutine is defines by:__
```python
  async def coroutine_function():

  call = coroutine_function()  -> 'This will return a coroutine object does not run the function()'
  result = await call  -> 'This is what is going to run the coroutine function'
```

### Tasks
  A way to schedule a coroutine to run as soon as possible allowing to run multiple coroutines
  awaiting coroutine functions directly will run them in order, scheduling task will alow them to run as soon as possible

__Creating a task:__
```python
  task1 = asyncio.create_task(coroutine_function())
  task2 = asyncio.create_task(coroutine_function())
  result1 = await task1
  result2 = await task2
  -> 'This runs the tasks concurrently'

  task1 = asyncio.create_task(coroutine_function())
  result1 = await task1
  task2 = asyncio.create_task(coroutine_function())
  result2 = await task2
  -> 'This runs the tasks one after the other'
```

__Using gather function:__
  Gather function does not handle errors it will proceed with all the functions given even if there is an error in one function
```python
  result1 = await asyncio.gather(coroutine_function1(), coroutine_function2()) -> 'Given functions will be automatically run concurrently and retun list of results in same order'
```

__Task groups :__
  Provides automatic error handling cancelling other tasks if a task failed
```python
tasks = []
async with asyncio.TaskGroup() as tg:
    task1 = tg.create_task(coroutine_function())
    tasks.append(task1) -> 'This is to collect results from the tasks if needed else it will just run it without any results showing'
    task2 = tg.create_task(coroutine_function())
    tasks.append(task2) -> 'Results from tasks will be added to the list in the same order and can be acessed outside'

results = [task.result() for task in tasks] -> 'create a list of results task.result() being the result of individual tasks'
```

### Lock
  Prevent multiple coroutines from acessing same resource/object

```python
  lock = asyncio,lock()

  async with lock:
      -> 'This will try to aquire the lock, If another coroutine holds it, the current one waits (yields control) until released'
```

### Semaphore

  Control how many task has access to same resource
```python
  semaphore = asyncio.Semaphore(n)
```

### Event
  Set a boolian flag to manage status of something
```python
  event = asyncio.Event()

  -> 'inside a coroutine_function add'
  await event.wait()  -> 'This will wait till the event is set'

 -> 'to set an event to true in another coroutine_function'
  event.set()
```
