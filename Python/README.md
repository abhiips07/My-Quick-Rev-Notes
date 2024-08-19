## built in functions
- `__class__`: to get the class of an object and to gets its name use `<object_variable>.__class__.__name__`
-  `id()` function returns a unique id for the specified object. All objects in Python has its own unique id. The id is assigned to the object when it is created.

## Operation on object functions
- `__init__`: same as constructor
- `__repr__`: to represent objects without ambiguity. Objects can be reconstructed from this form.
- `__str__`: human readable form representation of the objects. This is optional and if not defined then it is same as `__repr__`
- `__add__`: to add two objects
- `__mul__`: to multiply two objects

## decorator
A Python decorator is a function that takes another function (or method) as an argument, adds some functionality to it, and returns the modified function. Decorators are commonly used to modify the behavior of functions or methods in a clean and reusable way.

Defined like this
```python
def my_decorator(func):
    def wrapper(*args, **kwargs):
        # Code to be executed before the function call
        print("Before the function call")

        # Call the original function
        result = func(*args, **kwargs)

        # Code to be executed after the function call
        print("After the function call")

        return result
    return wrapper
```
apply it
```python
@my_decorator
def say_hello(name):
    print(f"Hello, {name}!")

# Call the decorated function
say_hello("Alice")

```

## asyncio
- At `await` keyword the code is blocked in a non blocking way and other things in eventloop are excuted until this function is done.
```python
import asyncio

# method 1
async def async_function():
    await asyncio.sleep(1)
    return "Hello, async!"

result = asyncio.run(async_function())
print(result)

# method 2
loop = asyncio.get_event_loop()
result = loop.run_until_complete(async_function())
print(result)

# mehtod 3
async def main():
    task = asyncio.create_task(async_function())
    result = await task
    print(result)

asyncio.run(main())
```
