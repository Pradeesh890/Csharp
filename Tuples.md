Tuple stores only a set of values (of any data type), but doesn't store property names.

so we should access them as Item1,Item2 etc. Which doesn't make sense sometimes.

Tuple supports up to 8 elements only by default.

we can store more than 8 values by using nested tuples (tuples inside tuples).

Tuples are mainly used to pass multiple values to a method as parameter, and also return multiple values from a method.

Value Tuple

Value type tuple is just normal tuple but the storage is stack instead of heap.

also value tuple supports named elements, we can give meaningful names to the elements, which dramatically improves code readability. These names are available through IntelliSense.

Mutability , unlike anonymous types, the elements of a value tuple are mutable public fields.

#### Deconstruction

Deconstruction is the process of "unpacking" the elements of a tuple into separate, distinct variables.

It provides convenient syntax to get the individual components of a grouped data structure into their own clearly named local variables.

```
(string name, int age) = GetUser();
```


#### Discard

A Discard, represented by the underscore character (\_), is a special placeholder variable that you use when you are required to provided a variable but you intentionally want to ignore its value.

The underscore is not a real variable with a memory location. It's a signal to the compiler that "a value will be produced here, but I don't care about it and will never use it." The compiler can often use this information to generate more efficient code by avoiding the allocation of memory for the discarded value.

