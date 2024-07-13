## built in functions
- `__class__`: to get the class of an object and to gets its name use `<object_variable>.__class__.__name__`
-  `id()` function returns a unique id for the specified object. All objects in Python has its own unique id. The id is assigned to the object when it is created.

## Operation on object functions
- `__init__`: same as constructor
- `__repr__`: to represent objects without ambiguity. Objects can be reconstructed from this form.
- `__str__`: human readable form representation of the objects. This is optional and if not defined then it is same as `__repr__`
- `__add__`: to add two objects
- `__mul__`: to multiply two objects